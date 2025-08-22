PostNL Chat -> Librechat with Bedrock backend
Add the mentioned functionality to PostNL chat and integrate that into explorer? Or make new chatbot for explorer. Could also do that with Librechat and bedrock backend.

Bedrock provides access to foundation models, guardrails, customizing top p/k, temperature, RAG, agents

Github has open source MCP server available https://github.com/github/github-mcp-server (that we would need to host ourselves e.g. on fargate) which can interact with the Github APIs
Atlassian has a remote MCP server available (not exactly sure if we can use this from our own app, but they are developing it fast).

MCP not really used for these types of workloads on serverless platform.

Opensearch/elastic search for the catalog

Small data -> include in prompt
Big data -> static -> RAG

Agentic workflow with tools (openapi spec)


