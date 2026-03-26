# Railway Deployment Recovery Checklist

Use this checklist when a Railway deploy fails, appears unstable, or looks
partially healthy.

## Step 1: Prove the Real State

Check all of these before changing config:

- Railway deploy status
- build logs
- live Railway URL
- custom domain

Mark each one as:

- healthy
- unhealthy
- unknown

If one surface works and another does not, do not call the deploy healthy.

## Step 2: Classify the Failure

Start with one likely class:

- lockfile/install failure
- wrong root or missing `package.json`
- invalid custom Railpack or Nixpacks override
- `502` / app not responding
- missing start command
- domain or target-port mismatch

Do not try to fix multiple classes at once.

## Step 3: Read the First Stable Error

Focus on the first repeatable error, not the noisiest one.

Common examples:

- `npm error code EUSAGE`
- `ENOENT /app/package.json`
- `No start command could be found`
- `install inputs must be an image or step input`
- `Application failed to respond`

## Step 4: Apply the Minimum Safe Fix

Good fixes are usually small:

- commit the correct lockfile
- correct the root directory
- restore the default Railway build path
- remove an invalid custom `railpack.json`
- fix `PORT` / host binding
- declare the correct start command

Avoid speculative layering:

- more custom build steps
- multiple config changes at once
- changing build and runtime together without proof

## Step 5: Verify Recovery

Recovery is only real when:

- CI is green
- Railway deploy is green
- live Railway URL is healthy
- custom domain is healthy or clearly out of scope
- the same error no longer appears

## Good Escalation Signal

Use a recovery audit if:

- the error changes after each attempted fix
- the deploy is red but the app seems partially alive
- custom build overrides are involved
- the team cannot tell whether the issue is build, runtime, or domain

---
If you go through these steps and still cannot isolate the issue, it usually means the failure is more context-specific.

You can send a short summary here: bayankulsnh@gmail.com
