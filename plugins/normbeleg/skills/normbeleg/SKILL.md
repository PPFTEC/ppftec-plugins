---
name: normbeleg
description: Use when the user works with EU electronic invoices: validating an XRechnung, EN 16931, Factur-X/ZUGFeRD or CIUS-RO (RO e-Factura) invoice, understanding a rule or error code such as BR-DE-15, converting invoice data to an e-invoice, or looking up e-invoicing mandates (Germany, Romania, Poland, France, Belgium). Not for tax or accounting advice.
---

# Normbeleg (EU e-invoices)

Normbeleg is a remote MCP server (`https://normbeleg.ppftec.com/mcp`) with five tools for e-invoice checks and e-invoicing mandates.

## When to use it
- Validate an invoice file against the official open-source validators.
- Explain a validation rule ID (EN 16931, XRechnung, CIUS-RO), for example one from an error a portal returned.
- Turn invoice data into an e-invoice (for example XRechnung UBL) and validate the result.
- Look up dated e-invoicing obligations for a country.

## When not to use it
- Tax, VAT or accounting advice, or deciding whether an invoice is legally valid for a tax authority.
- Formats that `list_supported_formats` does not list.

## Which tool first
- Unsure what is supported: `list_supported_formats` (formats, versions, size limits).
- A file or error code: `validate_einvoice`, then `explain_validation_rule` for each rule id.
- Creating one: `convert_invoice`.
- Obligations: `lookup_einvoice_mandate`.

Invoices can contain personal and commercial data: ask before sending real invoice content and prefer test data where possible. If the validator is still starting, retry after about a minute as the tool says.

## Sign-in
Claude shows a sign-in step when a tool needs one; a free account is enough. Free use has monthly and daily limits; pass on any limit message.

## How to present results
Results are technical checks and general information with dated official sources, not tax or legal advice. A passing validation is not proof that a tax authority or portal will accept the invoice. Keep rule ids and source links, and recommend an accountant or tax adviser for decisions.
