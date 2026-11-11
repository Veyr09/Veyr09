## Krystian Banys

AI red teamer and security engineer. I break AI systems and software for a living, then build the
tooling that makes the result measurable and the fix testable.

Two habits run through everything here, and they are the ones worth judging the work by:

- **A finding without a reproduction is not a finding.** Every issue I report comes with the input
  that triggers it and the output it produced, not a severity label.
- **A test that cannot fail proves nothing.** My suites run the same inputs through the broken code
  and the fixed code, and assert that the broken one actually breaks.

### AI red teaming

I compete in [Gray Swan Arena](https://app.grayswan.ai/arena/user/6a9ef958e1f2bbe20381c6f4), the
public red-teaming arena where frontier and anonymised models are attacked under fixed scenarios and
every break is judged by the platform. Record as of November 2026:

| | |
|---|---|
| Prize money won | **$1,400**, paid out: $1,000 for Indirect Prompt Injection: Black, Wave 1 Black Box, rank #18 · $300 for Hazard Hunt, Cyber track, rank #27 · $100 Lucky Break: Level Up |
| Global rank | #271, 38 unique breaks, 2,970 points |
| Volume | 7,542 judged submissions in the last year |
| Challenges | Indirect Prompt Injection: Black (86 breaks) · Hazard Hunt (189) · Lucky Break: Level Up (14, #51) · Lucky Break: Payday (5) · The Labyrinth (3, #95) |

Attack content stays private under the arena's rules. What I publish is the tooling and method:

**[redteam-ledger](https://github.com/Veyr09/redteam-ledger)** — the experiment ledger I run those
campaigns on. Payloads sealed by hash, every launch a run on a scenario × model cell, every verdict
with its source, and statistics that refuse to call something "falsified" on two samples. Ranks the
next launches, coordinates several agent sessions on one target. Node, zero dependencies, 512 tests.

### Detection and lab infrastructure

**[uacmon](https://github.com/Veyr09/uacmon)** — Windows token-integrity and UAC monitor with
UAC-bypass detection (MITRE T1548.002): elevated processes nobody consented to, auto-elevate registry
hijack keys, privileges being armed, weak UAC policy. Built from knowing how the bypasses work.

**[hyperv-isolated-lab](https://github.com/Veyr09/hyperv-isolated-lab)** — the lab I test in: a
Hyper-V workstation with no network path except a fail-closed WireGuard tunnel, with the audit
suites, measured leak tests, and every defect found along the way.

### Security and infrastructure

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

**[agent-readiness-scanner](https://github.com/Veyr09/agent-readiness-scanner)** — scores how well AI
shopping agents can read a storefront: robots and llms.txt, structured data, trust signals. 79 tests.

### Working with me

LLM red teaming · prompt injection · Windows internals · C · Rust · Java · Python · Node · Docker ·
Terraform · AWS · Linux

Available for fixed-scope work on
**[Upwork](https://www.upwork.com/freelancers/krystian)** — AI red-team assessments, security
reviews, container and deployment hardening, memory-safety audits, and cloud cost reviews. You get
the findings ordered by what they cost you, the reasoning behind each one, and the commands to re-run
it yourself.
