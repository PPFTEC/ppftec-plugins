---
name: normbeleg
description: Use when the user works with EU electronic invoices: validating an XRechnung, EN 16931, Factur-X/ZUGFeRD, CIUS-RO (RO e-Factura) or Polish KSeF FA(3) invoice, understanding a rule or error code such as BR-DE-15, converting invoice data to an e-invoice, or looking up e-invoicing mandates (Germany, Romania, Poland, France, Belgium). Not for tax or accounting advice.
---

# Normbeleg (EU e-invoices)

Normbeleg is a remote MCP server (`https://normbeleg.ppftec.com/mcp`) with five tools for e-invoice checks and e-invoicing mandates.

## When to use it
- Validate an invoice file against the official open-source validators. For Polish KSeF FA(3) this is a schema check only; KSeF upload rules are not checked.
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

Invoices can contain personal and commercial data: ask before sending real invoice content and prefer test data where possible.

The first `validate_einvoice` or `convert_invoice` call after an idle period is slow while the validator starts (measured 2 minutes 13 seconds on 20 November 2026). Tell the user this is normal. If it is still starting, the tool says to retry in about a minute and nothing is counted. The other three tools answer within seconds.

## Sign-in
`explain_validation_rule` and `list_supported_formats` work without an account. `validate_einvoice`, `convert_invoice` and `lookup_einvoice_mandate` need a free account: Claude shows a sign-in step when one of them is called. Free use has monthly and daily limits; pass on any limit message.

Full documentation: https://normbeleg.ppftec.com/mcp-docs

## How to present results
Results are technical checks and general information with dated official sources, not tax or legal advice. A passing validation is not proof that a tax authority or portal will accept the invoice. Keep rule ids and source links, and recommend an accountant or tax adviser for decisions.
