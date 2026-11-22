# eubinder

Claude Code plugin from PPFTEC S.R.L. It connects Claude to the EuBinder remote MCP server at `https://eubinder.ppftec.com/mcp` and adds a short skill that tells Claude when to use it and which tool to call first. Sign-in, when a tool needs it, is handled by Claude through OAuth; the plugin stores no keys. Results are general information with dated official sources, not legal advice.

- Docs: https://eubinder.ppftec.com/connect
- Privacy: https://eubinder.ppftec.com/mcp-privacy

Install: `/plugin marketplace add PPFTEC/ppftec-plugins` then `/plugin install eubinder@ppftec`.
