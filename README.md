# career-context

This repository implements a provider-neutral career context structure with thin adapters for OpenAI/Codex, Claude, Gemini, and Perplexity.

## Design principle

Three security boundaries, one provider-neutral schema, and four very thin provider adapters.

Recommended separation across repositories:

1. `personal-context`
2. `personal-work-context`
3. `career-context`

That separation reduces accidental leakage between personal, employer-confidential, and career-oriented material.

## Repository layout

```text
career-context/
├── README.md
├── AGENTS.md
├── CLAUDE.md
├── GEMINI.md
├── perplexity.md
├── context/
├── goals/
├── projects/
├── knowledge/
├── templates/
├── sources/
├── outputs/
├── archive/
└── scripts/
```

## Canonical content

The source of truth lives in:

- `context/`
- `goals/`
- `projects/`
- `knowledge/`

Provider files should stay short and route models to the relevant canonical files instead of duplicating the same context.

## Operating principles

- Keep facts, instructions, and source documents separate.
- Keep generated outputs out of canonical context.
- Record durable decisions in `goals/decisions.md`.
- Prefer small, focused Markdown files over a single large summary file.
- Never commit passwords, API keys, identity-document numbers, medical records, or raw financial statements.
- Encrypt especially sensitive material or exclude it entirely.
- Give each AI access only to the repository or subfolder needed for the task.
- Review stale context quarterly using `last_verified` metadata.

## Notes on repository scope

- `personal-context` should contain personal life context such as family, health, finances, housing, and personal goals.
- `personal-work-context` should contain current-employer material only when you are permitted to store it externally, and should be treated as highly confidential.
- `career-context` should contain CV material, achievements, job search context, interview stories, target roles, and professional development material.
