# Shoes Concept Test (Demo 1)

A footwear brand evaluates three running-shoe concepts across 30 personas spanning three consumer segments.

## Workflow

1. **Generate** 30 personas via `TinyPersonFactory.create_factory_from_demography(usa.json)` — 10 per segment.
2. **Simulate** 1-on-1 depth interviews with each persona in an isolated `TinyWorld`.
3. **Extract & analyze** structured results (preferred option + reasoning) via `ResultsExtractor`.

## Consumer segments

| Segment | Description |
|---|---|
| Serious Runner | 15+ miles/week, training for races |
| Casual Jogger | 1-2 times/week for health |
| Fashion-Conscious | Style-focused, occasional exercise |

## Concepts

- **A — Lightweight Comfort**: ultra-light, sleek, responsive cushioning
- **B — Soft Cushion Support**: high-cushion, impact protection, stable
- **C — Versatile Style**: balanced design, midweight cushioning, quality upper

## Example insights

The simulation surfaces **psychographic nuances** that simple demographics miss:

- A 74-year-old Serious Runner chose cushioning (B) over lightweight (A) due to joint issues.
- A CFO Casual Jogger chose lightweight (A) — his optimization mindset overrode his segment.
- A minimalist Fashion-Conscious shopper chose lightweight (A) for its sleek design.

## Running the notebook

```bash
export OPENAI_API_KEY=sk-...
jupyter lab TinyTroupe_shoes_demo.ipynb
```

The notebook defaults to `GENERATE_NEW_PERSONAS = False`, so it loads the pre-generated 30 personas from `exported_personas/` and runs the survey immediately. Flip to `True` to regenerate (requires API calls).

## Files

| File | Purpose |
|---|---|
| `TinyTroupe_shoes_demo.ipynb` | main notebook |
| `config.ini` | TinyTroupe configuration (v0.7.0 / gpt-5-mini) |
| `usa.json` | US demographics (from official TinyTroupe repo) |
| `exported_personas/` | 30 pre-generated personas |
| `result.csv` | survey results |
