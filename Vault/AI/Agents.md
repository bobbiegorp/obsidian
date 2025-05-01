| Agency Level | Description                                             | How that's called | Example Pattern                                    |
| ------------ | ------------------------------------------------------- | ----------------- | -------------------------------------------------- |
| ☆☆☆          | LLM output has no impact on program flow                | Simple processor  | `process_llm_output(llm_response)`                 |
| ★☆☆          | LLM output determines basic control flow                | Router            | `if llm_decision(): path_a() else: path_b()`       |
| ★★☆          | LLM output determines function execution                | Tool call         | `run_function(llm_chosen_tool, llm_chosen_args)`   |
| ★★★          | LLM output controls iteration and program continuation  | Multi-step Agent  | `while llm_should_continue(): execute_next_step()` |
| ★★★          | One agentic workflow can start another agentic workflow | Multi-Agent       | `if llm_trigger(): execute_agent()`                |
https://huggingface.co/blog/smolagents