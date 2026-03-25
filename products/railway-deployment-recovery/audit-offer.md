# Railway Deployment Recovery Audit

## What It Solves

This is a narrow service for broken or unstable Railway deploys.

It is a good fit when:

- the build is failing
- the app is unreachable or returns `502`
- custom build config may be involved
- the team needs a clear diagnosis and next fix path

## Included

- one incident diagnosis
- log and config review
- root-cause summary
- safe remediation plan
- verification checklist

## Not Included

- full infrastructure redesign
- ongoing DevOps management
- unrelated feature work
- multiple unrelated incidents in one engagement

## Best Fit

- indie founders
- solo developers
- small SaaS teams

## Typical Failure Families

- lockfile/install drift
- wrong root or missing `package.json`
- invalid custom Railpack override
- `502` / app-not-responding runtime mismatch
- missing or incorrect start command

## Deliverable

You leave with:

- the failure class identified
- the root cause clarified
- the next safe move made explicit

## Intake Requirements

Before starting:

1. repo link
2. Railway deployment link
3. build logs
4. current custom config files if any
5. whether the Railway URL works
6. whether the custom domain works

## Positioning

This is not broad DevOps consulting.
It is a focused Railway deployment recovery service.
