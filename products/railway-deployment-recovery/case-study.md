# Case Study: Railway Deployment Failed While the App Still Looked Partially Alive

## Summary

A Next.js frontend on Railway produced a confusing deployment incident:

- deploy checks failed
- some signals suggested the app might still be partially alive
- the visible error changed multiple times

The final root cause was not Railway itself.
It was an invalid custom `railpack.json` override that replaced a stable
default build path with a brittle one.

## Symptom

The deployment looked broken, but the situation was misleading.

Signals included:

- failed deploy status
- shifting build errors
- partial runtime-style signals

## False Leads

The incident surfaced in multiple phases:

1. `npm ci` / `EUSAGE`
2. `ENOENT /app/package.json`
3. invalid Railpack install input error

Each one looked like the root cause at first.

## Root Cause

The real problem was a custom `railpack.json` override that:

- replaced a stable default install/build path
- introduced invalid step behavior
- pushed the build into a misconfigured context

## Fix

The final safe fix was:

- remove the invalid custom `railpack.json`
- return to the default Railway / Nixpacks build path

## Verification

Recovery was only accepted after:

- deployment returned to green
- CI returned to green
- the error chain disappeared

## Lessons

- the first visible error is not always the root cause
- partial runtime signals can create false confidence
- custom build overrides should be justified, not guessed
- recovery starts with classification, not random config edits
