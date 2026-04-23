# Gen Z Skincare Concept Test (Demo 2)

A skincare brand evaluates three product concepts across 10 Gen Z US consumers (ages 18–28). For a parallel run on a different engine, see the [claude-persona genz-skincare demo](https://github.com/takechanman1228/claude-persona/tree/main/demo/genz-skincare).

## Workflow

1. **Generate** 10 Gen Z personas via `TinyPersonFactory.create_factory_from_demography(usa.json, population_size=10, ...)` — the Microsoft factory idiom.
2. **Discover** unprompted pain points by asking one open-ended question — *"When you're choosing skincare products, what frustrates you the most?"* — and saving the responses to `discovery.csv`.
3. **Simulate** a concept test: each persona reacts to all three concepts in an isolated `TinyWorld`.
4. **Extract** structured results (preferred option, reasoning, purchase likelihood, improvement) via `ResultsExtractor`; saved to `result.csv`.

## Concepts tested

- **A — Acne Control Serum**: fights breakouts with clinically proven actives
- **B — Barrier Repair Cream**: strengthens skin barrier and reduces redness
- **C — Glow Boosting Toner**: brightens dull skin and supports a more even complexion

## Discovery findings

The dominant frustration across the panel was **ingredient transparency** — vague claims, hidden active concentrations, and no easy way to verify efficacy before buying. 9 of 10 personas tagged their answer with the emotion `frustration`. See `discovery.csv` for per-persona detail.

## Concept-test result

| Run | A | B | C |
|---|---:|---:|---:|
| claude-persona baseline (Sonnet, hand-curated 10 personas) | 3 | 4 | **3** |
| TinyTroupe (`gpt-5-mini`, factory-generated 10 personas) | 3 | 5 | **2** |

Both C votes in the TinyTroupe run came from personas with skincare-adjacent identity (a freelance skincare Micro-Influencer and an undergraduate student). The functional concepts A (acne) and B (barrier repair) dominate — consistent with the discovery finding that the panel cares more about credible, transparent efficacy than aspirational glow.

## Running the notebook

```bash
export OPENAI_API_KEY=sk-...
jupyter lab TinyTroupe_genz_skincare_demo.ipynb
```

The notebook generates 10 Gen Z personas from `usa.json`, asks the discovery question, runs the concept test, and writes results to `discovery.csv` and `result.csv`. First run takes ~25–30 minutes (10 personas × 3 LLM rounds each plus extraction); reruns hit the simulation cache and are near-instant.

## Files

| File | Purpose |
|---|---|
| `TinyTroupe_genz_skincare_demo.ipynb` | main notebook (generate panel → discovery → concept test → comparison) |
| `config.ini` | TinyTroupe configuration (v0.7.0 / `gpt-5-mini`) |
| `usa.json` | US demographics (from official TinyTroupe repo) |
| `discovery.csv` | per-persona open-ended frustration responses |
| `result.csv` | per-persona concept-test results |
