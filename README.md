# Result Analyst

A Talent Market talent that owns **Stage 7 (Result Analysis)** of an
adversarial multi-stage research pipeline.

Given the Stage 5 pre-registration contract and Stage 6 raw results, it:

1. **Verifies the pre-registration contract is intact** — primary metric,
   statistical test, sample size, exclusions, and analysis pipeline all
   match what was locked before data collection.
2. **Ingests Stage 6 raw results** from the experiment-infra working
   directory (CSVs, JSONL, per-problem checkpoints).
3. **Runs the locked primary analysis only** — no fishing, no HARKing,
   no last-minute spec changes. Failure = REJECT.
4. **Reports effect sizes + confidence intervals** alongside p-values —
   never report a p-value bare.
5. **Produces `stage7_result_analyst.md`** — publication-grade results
   document with reproducibility receipts (seeds, package versions,
   exact command lines, McNemar contingency tables, etc.).

## Install

Register the repo URL on [Talent Market](https://one-man-company.com/):

```
Add Talent → paste https://github.com/YihangChen9/result-analyst
```

## Repo layout

```
result-analyst/
├── profile.yaml
├── DESCRIPTION.md
├── avatar.jpg
├── skills/
│   ├── core.md
│   └── result-analysis-runbook/
│       └── SKILL.md           full pre-registration-first analysis runbook
└── tools/
    └── manifest.yaml          uses host Read/Write/Bash for stats work
```

## Why temperature 0.3

Statistical analysis must be deterministic. The pre-registered procedure
defines a single correct answer; the talent is set to `temperature: 0.3`
to minimise variance in how it formats results and interprets tests, not
to "be creative" about which test to run.

## Upstream source

Extracted from the OneManCompany AutoResearch pipeline at
<https://github.com/Memento-Teams/Memento-Research>. The
`result-analysis-runbook/SKILL.md` is identical to that repo's
`src/onemancompany/default_skills/result-analysis-runbook/` version.

## License

See [LICENSE](./LICENSE).
