# Gen Z Skincare Concept Test (Demo 2)

A skincare brand evaluates three product concepts across 10 Gen Z US consumers (ages 18–28). For a parallel run on a different engine, see the [claude-persona genz-skincare demo](https://github.com/takechanman1228/claude-persona/tree/main/demo/genz-skincare).

## Workflow

1. **Generate** 10 Gen Z personas via `TinyPersonFactory.create_factory_from_demography(usa.json, population_size=10, ...)` — the Microsoft factory idiom.
2. **Simulate** a concept test: each persona reacts to all three concepts in an isolated `TinyWorld`.
3. **Extract** structured results (preferred option, reasoning, purchase likelihood, improvement) via `ResultsExtractor`.

## Concepts tested

- **A — Acne Control Serum**: fights breakouts with clinically proven actives
- **B — Barrier Repair Cream**: strengthens skin barrier and reduces redness
- **C — Glow Boosting Toner**: brightens dull skin and supports a more even complexion

## Headline result

| Run | A | B | C |
|---|---:|---:|---:|
| claude-persona baseline (Sonnet, hand-curated 10 personas) | 3 | 4 | **3** |
| TinyTroupe (`gpt-5-mini`, factory-generated 10 personas) | 4 | 5 | **1** |

The single C vote in the TinyTroupe run came from a persona whose occupation happened to be Beauty Advisor — a signal that **persona sampling structure matters as much as copy strength** for aesthetically-framed concepts.

## Running the notebook

```bash
export OPENAI_API_KEY=sk-...
jupyter lab TinyTroupe_genz_skincare_demo.ipynb
```

The notebook generates 10 Gen Z personas from `usa.json`, runs the concept test, and writes results to `result.csv`. First run takes ~3–5 minutes; reruns hit the simulation cache and are near-instant.

## Files

| File | Purpose |
|---|---|
| `TinyTroupe_genz_skincare_demo.ipynb` | main notebook (generate panel → concept test → comparison) |
| `config.ini` | TinyTroupe configuration (v0.7.0 / `gpt-5-mini`) |
| `usa.json` | US demographics (from official TinyTroupe repo) |
| `result.csv` | per-persona concept-test results |
