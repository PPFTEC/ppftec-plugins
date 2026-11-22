# normbeleg

Claude Code plugin from PPFTEC S.R.L. It connects Claude to the Normbeleg remote MCP server at `https://normbeleg.ppftec.com/mcp` and adds a short skill that tells Claude when to use it and which tool to call first. Sign-in, when a tool needs it, is handled by Claude through OAuth; the plugin stores no keys. Results are technical checks and general information with dated official sources, not tax or legal advice.

- Docs: https://normbeleg.ppftec.com/mcp-plans
- Privacy: https://normbeleg.ppftec.com/privacy#mcp

Install: `/plugin marketplace add PPFTEC/ppftec-plugins` then `/plugin install normbeleg@ppftec`.
