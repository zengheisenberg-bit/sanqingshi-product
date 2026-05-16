# Montique 山沁时 MVP

Static local MVP for the PRD v2.0 flow: selection table, advisor card, Feishu data handoff, and Canva SOP card.

## Files

- `index.html`: tea gift selection table.
- `advisor.html`: advisor business-card page.
- `sop-card.html`: printable A4 landscape inquiry SOP card.
- `data.json`: exported/converted gift box data.
- `assets/boxes/`: local product and logo-zone images.
- `DEPLOYMENT-CHECKLIST.md`: Feishu links, local run commands, and manual acceptance steps.

## Run

Open `index.html` or `advisor.html` directly in a browser. For the selection table, a local server is recommended because it fetches `data.json`:

```bash
python3 -m http.server 4173 -d montique-mvp
```

Then open:

```text
http://127.0.0.1:4173/index.html
http://127.0.0.1:4173/advisor.html
http://127.0.0.1:4173/sop-card.html
```

No build step, backend, API key, or framework is required.

## Scope Guardrails

Do not add internal/customer mode switching, customer-specific share links, long-image generation, recommendation statistics, search, sorting, price sliders, offline mode, Feishu API sync, or cloud deployment during MVP v2.0.

## Data Update

1. Export the Feishu `gift_boxes` online view as CSV.
2. Convert the CSV to the `data.json` shape.
3. Place product images under `assets/boxes/`.
4. Replace `data.json`.
5. Open `index.html` and verify filters, cards, and drawer.

## Montique Skills v1.1

Google Drive `skills` folder has been connected as an internal operations layer. See:

- `docs/montique-skills/README.md`
- `docs/montique-skills/FEISHU-SKILLS-INTEGRATION.md`

The v1.1 Skills add `packages` and `gift_solutions` for internal package intake and recommendation workflows. They do not replace the current MVP `gift_boxes` export until the solution library has enough verified, sellable records.

## Operator Tasks

- Maintain Feishu base and inquiry form from PRD sections 9.1-9.4.
- Replace generated placeholder product images with real normalized 1200x1200 product images from PRD section 8.4.
- Use `sop-card.html` as the internal SOP card source, or import its copy into Canva for final static PNG/PDF styling.
- Publish the Feishu form and replace `CONFIG.inquiry_form_url` in `advisor.html` if the public form URL differs from the internal form URL.

## Current Feishu Deployment

- Base: `https://ccni7miiwrh3.feishu.cn/base/Jf6zbAO8paZf6TsUY77cHiIhnwc`
- Public form: `https://ccni7miiwrh3.feishu.cn/share/base/form/shrcnFBuojqdY0XmFZ9VSgoeI5c?source=mingpian`

## Verification

- `data.json` parses.
- `index.html` renders 10 records and filters them.
- Detail drawer does not display `internal_note`.
- `advisor.html` reads visible data from `CONFIG`.
- 390px mobile width has no horizontal scrollbar.
