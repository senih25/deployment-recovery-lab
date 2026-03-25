# Railway Deployment Recovery

Evidence-based recovery resources for Railway deployment failures.

This is the first narrow product inside Deployment Recovery Lab. It packages
real Railway incident patterns into simple, usable materials for founders and
developers who need to recover broken deploys without guessing.

## What This Product Contains

- `checklist.md`
  - a practical Railway deployment recovery checklist
- `case-study.md`
  - a real incident walkthrough with symptom, false leads, root cause, fix,
    and verification
- `audit-offer.md`
  - a narrow paid recovery service outline
- `landing-copy.md`
  - short marketing copy for a landing page or service page
- `faq.md`
  - clear answers for common pre-sale questions

## Who This Is For

- indie founders
- solo developers
- small SaaS teams

This product is not a general DevOps resource library.
It focuses on repeated Railway deployment recovery problems such as:

- lockfile/install drift
- missing `package.json` or wrong root directory
- invalid custom Railpack overrides
- `502` / app-not-responding runtime mismatch
- missing or incorrect start command

## What This Is Not

- not an official Railway resource
- not a substitute for Railway support
- not a full platform engineering service

## Working Principle

The recovery method here is:

1. prove the real service state
2. classify the failure family
3. read the first stable error
4. apply the minimum safe fix
5. verify recovery

## Recommended Starting Path

1. Read [`checklist.md`](./checklist.md)
2. Read [`case-study.md`](./case-study.md)
3. If the issue is still unclear, use [`audit-offer.md`](./audit-offer.md)

## Commercial Note

This product supports a narrow service-first offer.
It does not assume that a validator, CLI, or GitHub Action should exist yet.

## Source Integrity

These materials are built from:

- documented deployment incidents
- public Railway docs and community discussions
- repeated failure patterns observed in real projects

Claims should remain evidence-based and conservative.
