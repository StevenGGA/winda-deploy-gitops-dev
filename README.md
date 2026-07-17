# winda-deploy-gitops-template

A clean, minimal **GitOps repo for local development** of [winda-deploy](https://github.com/winda-ai/winda-deploy-api) on a local `kind` cluster.

> ⚠️ **Don't fork this, and don't use it in production.** Click **"Use this template"** to create your *own* copy, then follow the step-by-step guide in `winda-deploy-api/docs/local-dev.md`. This is deliberately empty of any production state (no linode clusters, no real secrets, no real domains).

## What's here
- `clusters/registry.yaml` — the env→cluster map, pointing at **one** cluster: your local `kind` (env `dev`).
- `clusters/kind/apps/` — where the winda-deploy api will write your deployments/routes (starts empty).
- `catalog/` — where app definitions land (starts empty).
- `infrastructure/kind/` — namespaces (`dev`/`beta`/`prod`/`winda-deploy`) for the local cluster.

The Flux `GitRepository` + `Kustomization` objects are **not** committed here — the local-dev bootstrap creates them pointing at *your* copy of this repo (see the guide).
