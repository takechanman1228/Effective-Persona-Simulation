# Gen Z Skincare Concept Test (Demo 2)

A skincare brand evaluates three product concepts across 10 Gen Z US consumers (ages 18–28). Parallels the [`claude-persona/demo/genz-skincare/`](../../../claude-persona/demo/genz-skincare/) experiment under a different engine for side-by-side comparison.

## Workflow

1. **Load** 10 Gen Z personas pre-generated via `TinyPersonFactory.create_factory_from_demography(usa.json, population_size=10, additional_demographic_specification="10 Gen Z skincare shoppers in the US.")` — the Microsoft factory idiom.
2. **Simulate** a concept test in three stages, each with a different C-copy variant.
3. **Extract & compare** results against the claude-persona baseline.

## Concepts tested

- **A — Acne Control Serum**: fights breakouts with clinically proven actives
- **B — Barrier Repair Cream**: strengthens skin barrier and reduces redness
- **C — Glow Boosting Toner**: three copy variants tested
  - **C1**: "brightens dull skin and evens skin tone"
  - **C2**: "brightens dull skin and supports a more even complexion"
  - **C3**: "visibly brightens dull skin for a radiant, even complexion"

## Headline result

| Run | A | B | C |
|---|---:|---:|---:|
| Claude-persona baseline (Sonnet, hand-curated 10 personas) | 3 | 4 | **3** |
| C1 ("evens skin tone") | 4 | 6 | **0** |
| C2 ("supports a more even complexion") | 4 | 5 | **1** |
| C3 ("visibly brightens…radiant even complexion") | 4 | 6 | **0** |

Only C2 unlocks a vote for Concept C under `gpt-5-mini`, and even then only from one persona whose occupation happens to be Beauty Advisor — a signal that **persona sampling structure matters more than copy strength** for aesthetically-framed concepts.

Full writeup: [`../../../Doc/2026-04-21_tinytroupe_genz_skincare_learnings.md`](../../../Doc/2026-04-21_tinytroupe_genz_skincare_learnings.md).

## Running the notebook

```bash
export OPENAI_API_KEY=sk-...
jupyter lab TinyTroupe_genz_skincare_demo.ipynb
```

The notebook loads the 10 pre-generated personas from `exported_personas/`, runs Stage 1 (C1), conditionally runs Stage 2 (C2) if C1 scored 0 for C, then always runs Stage 3 (C3). Results are written to `result_concept_c{1,2,3}.csv`.

## Files

| File | Purpose |
|---|---|
| `TinyTroupe_genz_skincare_demo.ipynb` | main notebook (3-stage concept test) |
| `config.ini` | TinyTroupe configuration (v0.7.0 / gpt-5-mini) |
| `usa.json` | US demographics (from official TinyTroupe repo) |
| `exported_personas/` | 10 pre-generated Gen Z personas |
| `result_concept_c{1,2,3}.csv` | results per stage |
