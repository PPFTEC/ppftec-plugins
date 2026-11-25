---
name: shieldbook
description: "Use when the user asks about the EU Cyber Resilience Act (CRA): whether it applies to a product, its product class, Article 14 reporting deadlines for actively exploited vulnerabilities or severe incidents, technical documentation, SBOMs, vulnerabilities in SBOM components, or security.txt. Not for NIS2, GDPR or AI Act questions."
---

# Shieldbook (EU Cyber Resilience Act)

Shieldbook is a remote MCP server (`https://shieldbook.ppftec.com/mcp`) with read-only CRA tools.

## When to use it
- Does the CRA (Regulation (EU) 2024/2847) apply to a software or hardware product, and which class?
- When are the Article 14 reports due after an actively exploited vulnerability or severe incident?
- What must the technical documentation (Annex VII) contain?
- What does an SBOM (CycloneDX or SPDX JSON) list, and which components have known vulnerabilities?
- Generate SBOM steps for CI, or a security.txt file.

## When not to use it
- Other laws (NIS2, GDPR, AI Act), a conformity assessment, or a decision that needs a lawyer.
- SBOMs in XML or tag-value format.
- Submitting reports: the tools submit nothing to ENISA or a CSIRT; cra_report_draft returns content for the manufacturer to review and submit on ENISA's Single Reporting Platform.

## Which tool first
- Scope: `cra_scope_check` with `answers` set to `{}`; ask the user each returned question, then call it again with the answers so far. `cra_scope_questions` lists all questions at once.
- Deadlines: `cra_reporting_deadlines`, then `cra_report_draft` for report contents.
- Documentation: `cra_technical_documentation_checklist`.
- SBOM: `sbom_summarize`, then `sbom_vulnerabilities`; `sbom_ci_snippet` and `security_txt_generate` for generated files.
- Privacy: sbom_vulnerabilities sends the components' package URLs (type, name, version) to OSV.dev, including the names of private or internal packages; say so before sending an SBOM that lists them.

## Sign-in
cra_scope_questions, cra_scope_check and cra_reporting_deadlines work without an account, with a daily limit per network; the other tools ask the user to sign in, and Claude shows the sign-in step. If a tool answers with a limit message, pass it on.

## How to present results
Results are general information with dated official sources, not legal advice. Quote the version or verification date the tool returns, keep the cited articles, and tell the user to consult a qualified lawyer for decisions about their obligations. Do not say a product is "compliant" or "certified".
