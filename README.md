# Takarda Design — Decision Dossier Repository

Design-only submission for the National Secondary Certificate Council results and verification platform (Takarda). **No application was built.** Paper decisions only.

## Structure

```
takarda-design/
├── README.md                 ← this file
├── api/
│   └── openapi.yaml          ← OpenAPI 3.0.3 (validates with Redocly CLI)
├── diagrams/
│   ├── c4-context.drawio
│   ├── c4-container.drawio
│   └── c4-component-check-path.drawio
├── dossier/
│   └── software submission.pdf
|   ├── Software Submission.docx
└── ai/
    └── ai-log.md
```

## Validate the API contract

```bash
npx @redocly/cli lint api/openapi.yaml
```

Expected: valid (warnings only are acceptable).

## Open diagrams

1. Go to https://app.diagrams.net  
2. File → Open from → Device → select the `.drawio` file  
3. Export PNG/SVG for inclusion in the PDF if needed; keep `.drawio` as source of truth in this repo

## Dossier

The decision dossier PDF is in `dossier/`. It contains Parts A–E in the order required by the brief, plus the one-page executive decision summary (read first).

## Contact / defence

Any decision in the dossier may be challenged orally. Reverse signals and named victims are intentional.
