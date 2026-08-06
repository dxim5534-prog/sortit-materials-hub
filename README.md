# SORT IT Materials Hub (Phase 0)

Static materials site for the SORT IT Timor-Leste training programme.
Spec: `SORT iT Training/05_PLATFORM/MATERIALS-HUB-IA.md`.

- Preview locally: `pip install mkdocs-material` then `mkdocs serve`
- Build: `mkdocs build --strict`
- Deploy: push to `main` → GitHub Actions (or connect the repo to Cloudflare Pages)

Rules that keep links immortal: topic-based slugs (never session numbers), URLs are
never deleted, new file versions replace files behind the same path, cohort pages link
INTO materials (materials stay cohort-agnostic). Facilitator answer keys are never
published here.
