# Part E — AI Usage Log

AI was used throughout design (requirements wording, architecture options, OpenAPI sketch, query reasoning). The brief requires at least one case where AI output was checked, found wrong, and corrected. That case is recorded first.

## Mandatory correction (AI was wrong)

| Field | Detail |
|-------|--------|
| **Date** | 2026-09-28 |
| **Tool** | Grok (architecture coaching session) |
| **Task** | Draft OpenAPI 3.0.3 security scheme for employers’ association mTLS |
| **AI claim** | Used `type: mutualTLS` under `components.securitySchemes` |
| **How checked** | Ran `npx @redocly/cli lint api/openapi.yaml` |
| **Finding** | **Error:** OpenAPI 3.0.3 allows only `apiKey`, `http`, `oauth2`, `openIdConnect`. `mutualTLS` is valid in OpenAPI 3.1, not 3.0.3. Spec failed validation. |
| **What was actually true** | For a 3.0.3 contract, mTLS must be described as edge/transport policy (and optionally represented with a non-normative scheme or extension), not as `type: mutualTLS`. |
| **Decision** | Removed invalid `mutualTLS` type. Documented association mTLS in the API description and info block as **edge-enforced client certificates**. Kept Bearer for human verifiers/schools. Spec now validates. Design intent (machine ≠ person auth) unchanged. |

This is the required “AI was confident and incorrect; human verification changed the artefact” entry.

## Other AI-assisted tasks (summary)

| Date | Tool | Task | Outcome |
|------|------|------|---------|
| 2026-09-25 | Grok | BRD / PRD / FRD / WBS drafts | Accepted structure; numbers taken only from brief; edited for board vs builder vs tester voice |
| 2026-09-28 | Grok | Conflict list and impossible request | Accepted: Ops “rewrite already-verified certificates” marked impossible; append-only + future-read consistency offered instead |
| 2026-09-28 | Grok | C4 Mermaid then draw.io | Diagrams retained; “deliberately left out” paragraphs added per brief |
| 2026-09-28 | Grok | Five query predictions | Row-first walkthroughs retained; Query 5 “contains” limitation and “need not be fast” kept after cross-check with B-tree behaviour |
| 2026-09-29 | Grok | OpenAPI lint fix | See mandatory correction above |

## Method

- Every number in the dossier is from the brief, calculated from the brief, or labelled ESTIMATE/ASSUMPTION.
- AI suggestions that introduced generic reasons (“microservices are complex”) were rejected; only Takarda-specific rejection properties were kept.
- No application or database was built; AI was not used to generate runnable code for submission.
