# Link Anchor Checker

We need to check a site for internal consistency, for the Google SEO

If our site has anchor links to itself that don't resolve to real anchor
targets, then Google (and others) will penalize us in the search ranking.

## The End

When you adapt this Kubernetes Operator for your own purposes, you will likely
start by forking this repo. Find `.github/workflows/publish.yaml` which will
require some changes to point at your fork in order to use it independently.

The GitHub Actions workflow is based on `workflow_dispatch` triggers. You are
meant to run these four triggers in order to populate your Git repo:

* target: `base` cache: `''` (blank)
* target: `gems` cache: `base`
* target: `gem-cache` cache: `gems`
* target: `deploy` cache: `gems`

When you have populated the `gem-cache`, it is intended to be used as a cache
by manual selection for the `gems ` target, triggered manually. This way you
can update the gems without rebuilding everything.

## Why Web Assembly

Not using Web Assembly this time - note this doesn't change the design much!
