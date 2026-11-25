---
name: eubinder
description: "Use when the user sells online into the EU and asks which EU rules may apply to their shop: product safety information (GPSR) and the EU responsible person, toys and cosmetics, packaging (PPWR) and national packaging registers (EPR), accessibility (European Accessibility Act), or wants a draft GPSR product-page block or accessibility statement. Not for taxes other than e-invoicing or for judging a specific product."
---

# EuBinder (EU rules for online shops)

EuBinder is a remote MCP server (`https://eubinder.ppftec.com/mcp`) with read-only tools for EU rules that may apply to online shops.

## When to use it
- Which EU and national obligations may apply to a shop selling into given EU countries.
- Where and how to register as a packaging producer in a given country.
- Explain one rule in detail, by its rule id.
- Draft the GPSR Article 19 product-page safety block or an accessibility statement.
- Write the GPSR block in English, German, French, Dutch, Italian, Spanish, Polish or Romanian.

## When not to use it
- Assessing whether a specific product is safe.
- Product sectors other than toys and cosmetics; VAT or other taxes (B2B e-invoicing dates are covered); data protection or cookies; rules of countries outside the EU; a legal opinion.

## Which tool first
1. `eu_obligations_checklist` with the EU countries the shop ships to (add where the business is established, categories and business answers to refine). Call `list_markets_and_categories` first only when unsure of the accepted values, or to find a `rule_id` without an account: it also lists every rule id with its title.
2. `explain_obligation` for one rule, by a rule_id from the checklist or from list_markets_and_categories; `epr_packaging_register_lookup` for one country's register.
3. `gpsr_product_page_block` and `accessibility_statement_draft` for drafts, using only details the user gives.

## Sign-in
The three general tools (`list_markets_and_categories`, `explain_obligation`, `epr_packaging_register_lookup`) work without an account. The other tools ask the user to sign in.

## How to present results
Results are general information with dated official sources, not legal advice. Keep the status, dates and source links the tool returns, point out entries marked unverified, and tell the user that drafts need review before publication. Do not say a shop is "compliant".
