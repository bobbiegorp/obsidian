Transformer architecture was introduced in 2017 by a Google research paper "Attention Is All You Need". They simplified existing architectures by stripping them of recurrence and convolutions and only focusing on the attention mechanism. This attention mechanism is at the core of the transformer architecture.

The basic transformer (encoder or decoder) is a stack of identical layers, each with:

- **Multi-head self-attention**: Several attention mechanisms run in parallel to capture different types of relationships.
- **Feedforward layer**: A small MLP applied to each position.
- **Layer normalization** and **residual connections**: For stability and gradient flow.


Attention mechanism:
Traditionally, models like RNNs and LSTMs processed sequences **one element at a time**, which limited parallelism and struggled with long-range dependencies.

Transformers ditched recurrence entirely and introduced:
 **Self-attention**: Each token in a sequence can "attend" to all other tokens at once, learning **contextual relationships** between elements directly.

Sub architectures:

| Architecture        | Attention Type          | Output Type          | Typical Use Cases                      |
| ------------------- | ----------------------- | -------------------- | -------------------------------------- |
| **Encoder-only**    | Bidirectional           | Context embeddings   | Text classification, understanding     |
| **Decoder-only**    | Causal (autoregressive) | Next token           | Text generation, chatbots, coding      |
| **Encoder-Decoder** | Mixed (bi + causal)     | Sequence-to-sequence | Translation, summarization, captioning |

Encoder-Decoder
	Encode input to a sequence of hidden representations (embeddings) and decodes the hidden representations to an output sequence.
 
Encoder-only
	Input sequence is encoded to context embeddings that capture meaning of tokens in the specific context. 

Decoder-only
	Input embeddings are decoded to predict the next most likely token. Process is repeated until some stop condition, such as max length. 

For clarification: encoder-decoder vs decoder-only

|Model Type|What's Decoded?|
|---|---|
|Encoder-Decoder|A separate target sequence, conditioned on an encoded input|
|Decoder-Only|The **next token** in a single sequence, based on past tokens|


Chatbot is a decoder-only transformer architecture that roughly works like this:
1. Input prompt is tokenized and each token is mapped to an embedding. This is a simple mapping: after training the model, each token is assigned a fixed embedding through a learned embedding matrix that has size vocab_size x embedding dimension. A positional embedding is added to each token embedding to encode the **position** of the token in the sequence (as transformers have no inherent notion of order). This is regarded as an input processing step and is not a core part of the transformer architecture because there is no self-attention mechanism in this step. Hence it is a decoder-only transformer architecure. 
   
   Sidenote: many chatbots use subword tokenization, i.e. it is not necessarily true that one word equals one token. For example, the word 'cat' may be one token, but the word 'unbelievable' may be tokenized as ['un', 'believ', 'able'] (just an example). In this way the vocabulary sized is is decreased by a lot compared to full word tokenization, and the meaning of rare, complex compounds can be (partly) inferred from its subwords (word “antidisestablishmentarianism” might not exist as a full token, but subwords like “anti”, “dis”, “establish” allow the model to understand it). One of the ways to create a vocabulary of tokens is Byte Pair Encoding (BPE): This 1. starts with characters as base units, 2. iteratively merges the most frequent adjacent pairs into new tokens, and 3. builds up a vocabulary of common subwords.
2. The embeddings are fed to the decoder stack, where causal (autoregressive) self-attention is applied (model starts paying attention to previous tokens in the sequence, obviously only previous tokens can be attended to as that is all we have) and a next most likely token is predicted. This results in a probability distribution of next most likely tokens, from which a token is sampled (temperature and top-p/top-k influence this sampling).
3. This sampled token is appended to the input and the process starts again to generate the token after. This process repeats until some stop-condition is met, such as max-length.


