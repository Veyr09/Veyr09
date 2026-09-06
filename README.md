## Krystian Banys

Security and infrastructure. I find what is wrong with a system, prove it, fix it, and leave a test
behind so the fix cannot quietly regress.

Two habits run through everything here, and they are the ones worth judging the work by:

- **A finding without a reproduction is not a finding.** Every issue I report comes with the input
  that triggers it and the output it produced, not a severity label.
- **A test that cannot fail proves nothing.** My suites run the same inputs through the broken code
  and the fixed code, and assert that the broken one actually breaks.

### What is here

**[security-and-infrastructure-labs](https://github.com/Veyr09/security-and-infrastructure-labs)** —
ten small projects, each a real problem built and broken on purpose, then fixed, with the evidence
kept.

| | |
|---|---|
| Memory safety in C | Five defects — CWE-787, 193, 122, 416, 134 — reproduced under AddressSanitizer and closed, including one the sanitizer never catches |
| XXE in Java | What `DocumentBuilderFactory` and `XMLInputFactory` do out of the box, and the settings that stop it |
| Multi-tenant isolation | One service deployed three ways, probed for cross-tenant reads and session replay |
| Docker port hardening | A container published on every interface, closed and then verified *from outside the machine* |
| Flask API review | Eight defects found, each proven by a test that attacks both copies |
| AWS cost from a Terraform plan | $1,460.20/month of fixed cost read off a plan, before anything is built |
| Four data tools | CSV validation in Rust, spreadsheet cleanup, a rates sync, a scraper |

**[gitlab-security-research](https://github.com/Veyr09/gitlab-security-research)** — source-driven
review of GitLab's authorization architecture under its public bug bounty program. I mined 400
disclosed reports to find which bug class actually gets paid, then hunted that class in newly shipped
code. 21 hypotheses traced through the source to a verdict, and why each one is a dead end.

### Working with me

C · Rust · Java · Python · Docker · Terraform · AWS · Linux

Available for fixed-scope work on
**[Upwork](https://www.upwork.com/freelancers/krystian)** — security reviews, container and
deployment hardening, memory-safety audits, and cloud cost reviews. You get the findings ordered by
what they cost you, the reasoning behind each one, and the commands to re-run it yourself.
