# PPFTEC plugins for Claude Code

A plugin marketplace from PPFTEC S.R.L. Each plugin connects Claude to the remote MCP server of one PPFTEC product and adds a short skill that tells Claude when to use it and which tool to call first. Sign-in, where a tool needs it, is handled by Claude through OAuth; the plugins contain no keys or headers.

## Install

```
/plugin marketplace add PPFTEC/ppftec-plugins
/plugin install shieldbook@ppftec
/plugin install eubinder@ppftec
/plugin install bandplain@ppftec
/plugin install normbeleg@ppftec
```

Or from a shell: `claude plugin marketplace add PPFTEC/ppftec-plugins`, then `claude plugin install <plugin>@ppftec`. Install only the plugins you need.

## Plugins

| Plugin | What it does | MCP server | Docs | Privacy |
|---|---|---|---|---|
| shieldbook | EU Cyber Resilience Act (CRA): scope check, Article 14 reporting deadlines, technical documentation checklist, SBOM and vulnerability tools | https://shieldbook.ppftec.com/mcp | [docs](https://shieldbook.ppftec.com/mcp) | [privacy](https://shieldbook.ppftec.com/privacy) |
| eubinder | EU rules for online shops: GPSR, PPWR and national packaging registers, accessibility | https://eubinder.ppftec.com/mcp | [docs](https://eubinder.ppftec.com/connect) | [privacy](https://eubinder.ppftec.com/mcp-privacy) |
| bandplain | EU pay transparency: job-ad pay ranges, pay-information request deadlines, pay-gap figures | https://bandplain.ppftec.com/mcp | [docs](https://bandplain.ppftec.com/mcp/docs/) | [privacy](https://bandplain.ppftec.com/privacy/mcp/) |
| normbeleg | EU e-invoices: validate XRechnung, ZUGFeRD/Factur-X and RO e-Factura, explain rules, look up mandates | https://normbeleg.ppftec.com/mcp | [docs](https://normbeleg.ppftec.com/mcp-plans) | [privacy](https://normbeleg.ppftec.com/privacy#mcp) |

Some tools work without an account; others ask you to sign in (all Bandplain and Normbeleg tools do). Limits are described on each product's docs page.

## Information, not legal advice

Results are general information with dated official sources. They are not legal, tax or accounting advice and do not certify compliance. Ask a qualified professional before relying on them for a decision.

## Licence

See [LICENSE](LICENSE): all rights reserved; use through Claude Code from this marketplace is allowed; copying, modification and redistribution need written permission.

## Sources

Read on 2026-11-22. The docs define `license` in plugin.json as an SPDX identifier and name no value for a proprietary package, so the field is omitted; each plugin folder carries a copy of LICENSE instead (the directory checklist requires a LICENSE file or the field).
- https://code.claude.com/docs/en/plugins-reference (plugin manifest) and https://code.claude.com/docs/en/plugins/manifest-reference.md
- https://code.claude.com/docs/en/plugins/create-marketplace.md and https://code.claude.com/docs/en/plugins/marketplace-reference.md
- https://code.claude.com/docs/en/plugins/components.md and https://code.claude.com/docs/en/mcp
- https://code.claude.com/docs/en/plugins/publish.md
- https://claude.com/docs/plugins/pre-submission-checklist, https://claude.com/docs/plugins/submit, https://claude.com/docs/directory/publish
- Product facts: the four docs pages in the table above and each server's `tools/list`, read 2026-11-22.

Docs versus the internal note (mcp-agent-engagement-2026-11-22.md, section 1.4): the note says community-marketplace entries are submitted to Anthropic. The docs say the directory takes a plugin bundle from a public GitHub repository through the developer portal (claude.ai/directory/manage); the "community marketplace" is not a submission route in the pages read. The docs were followed.
