# kanay-quarto-templates

Quarto document templates for Kanay, with Kami design tokens applied.

## Structure

```
├── _quarto.yml              # Project config (theme: none + Kami CSS)
├── styles/
│   └── kami-tokens.css      # 56 CSS custom properties
├── templates/
│   └── _template-facility-report.qmd
└── liveanalysis/
    └── _output/             # Rendered HTML (gitignored)
```

## Design Tokens

Tokens are from the Kami design system (from `open-design/design-systems/kami/tokens.css`).
They are injected into rendered HTML at render time — no build step needed.

## Usage via API

```bash
# Inline preview
curl -X POST http://100.84.140.29:8767/quarto/preview \
  -H "Content-Type: application/json" \
  -d '{"qmd_content": "---\ntitle: Test\n---\n# Hello {{NAME}}", "params": {"NAME": "World"}}'

# Render from template
curl -X POST http://100.84.140.29:8767/quarto/render \
  -H "Content-Type: application/json" \
  -d '{"template": "templates/_template-facility-report.qmd", "params": {"FACILITY_NAME": "Eurostar"}}'
```

## RStudio Access

Cloned to `/home/kanayr/quarto-templates/` on ex44.
Access via RStudio Server at `http://100.84.140.29:8787` (user: `kanayr`).
