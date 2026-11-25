---
name: bandplain
description: "Use when the user asks about pay transparency rules: whether a job ad must show pay, checking a job ad against those rules, which pay range to post, the deadline to answer an employee's pay-information request and what the answer covers, gender pay-gap reporting rules for a company size, a gender pay gap from aggregated figures, or the transposition status of the EU Pay Transparency Directive (EU countries, US states and Canadian provinces covered by the tool). Not for individual salary advice."
---

# Bandplain (pay transparency)

Bandplain is a remote MCP server (`https://bandplain.ppftec.com/mcp`) with read-only pay-transparency tools built on a versioned rule pack.

## When to use it
- Must a job ad in a given jurisdiction state the pay, and what may be asked of candidates?
- Check a job ad text against the rules, or suggest a pay range to post.
- By when must an employer answer a pay-information request received on a given date?
- Compute a gender pay gap from aggregated counts and mean or median pay per category.
- Which gender pay-gap reporting rules apply to an employer of a given size, and how often?
- What must an answer to a worker's or applicant's pay-information request cover? (an outline with placeholders, no figures)
- Which EU member states have transposed Directive (EU) 2023/970, according to official sources?

## When not to use it
- Individual salary advice or anything that needs a named person's data.
- Jurisdictions that `list_jurisdictions` does not return.

## Which tool first
1. `list_jurisdictions` to get the jurisdiction code the other tools need.
2. `get_job_ad_rules`, `check_job_ad`, `suggest_ad_range`, `pay_request_deadline`, `pay_request_reply_outline`, `gap_reporting_rules`, `pay_gap_from_aggregates`, or `eu_transposition_status`.

Do not send names or other personal data. Remove contact details from ad text. Text checks of a job ad are heuristics; bands based on fewer than 5 people are refused.

## Sign-in
`list_jurisdictions` and `get_job_ad_rules` also work without an account, with lower limits. The other tools need sign-in; Claude shows a sign-in step when a tool needs one. The server is for people aged 18 or over using it for their business or profession; the consent page explains the terms.

## How to present results
Results are general information with dated official sources, not legal advice. State the rule-pack version and the date the rules were verified, keep the cited provisions and links, and say when the tool reports that the law does not answer the question. Recommend a qualified employment lawyer for decisions about obligations.
