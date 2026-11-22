---
name: bandplain
description: Use when the user asks about pay transparency rules: whether a job ad must show pay, checking a job ad against those rules, which pay range to post, the deadline to answer an employee's pay-information request, or a gender pay gap from aggregated figures (EU countries, US states, Canadian provinces covered by the tool). Not for individual salary advice.
---

# Bandplain (pay transparency)

Bandplain is a remote MCP server (`https://bandplain.ppftec.com/mcp`) with read-only pay-transparency tools built on a versioned rule pack.

## When to use it
- Must a job ad in a given jurisdiction state the pay, and what may be asked of candidates?
- Check a job ad text against the rules, or suggest a pay range to post.
- By when must an employer answer a pay-information request received on a given date?
- Compute a gender pay gap from aggregated counts and mean or median pay per category.

## When not to use it
- Individual salary advice or anything that needs a named person's data.
- Jurisdictions that `list_jurisdictions` does not return.

## Which tool first
1. `list_jurisdictions` to get the jurisdiction code the other tools need.
2. `get_job_ad_rules`, `check_job_ad`, `suggest_ad_range`, `pay_request_deadline`, or `pay_gap_from_aggregates`.

Do not send names or other personal data. Remove contact details from ad text. Text checks of a job ad are heuristics; bands based on fewer than 5 people are refused.

## Sign-in
Claude shows a sign-in step when a tool needs one. The server is for people aged 18 or over using it for their business or profession; the consent page explains the terms.

## How to present results
Results are general information with dated official sources, not legal advice. State the rule-pack version and the date the rules were verified, keep the cited provisions and links, and say when the tool reports that the law does not answer the question. Recommend a qualified employment lawyer for decisions about obligations.
