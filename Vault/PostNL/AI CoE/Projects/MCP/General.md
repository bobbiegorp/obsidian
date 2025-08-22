History:

Jeroen munter Digital was pushing for more security in MCP asking for guidance to AI COE

Adapter to transform internal APIs as MCP servers

Giving teams and customers possibility to use the APIs as tools 

First focus on public apis like t&t, locatiewijzer, bigger reach and more customers

Integrate in servers and clients (?) cursor, vscode and chatgpt

Based on reference arch from aws -> only lambda (no longer ecs) (maybe fastmcp on ecs or if possible can see if we can run it on Lambda)

Everything is typescript at the moment (but python is available)

MCP runs on std/io (cli). sse (http with open connection, not in the picture). http (that's how it's used now) ALB -> auth with cognito -> Lambda -> LLM response. (web based security)

explore repo, connect to client, play a bit

chatgpt integration

claude desktop (easiest client, trial?)
cursor (connect mcp without pro)


eva van baarle -> good to get her involved in the locatiewijzer mcp project

