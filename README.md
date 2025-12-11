# Effective Persona Simulation with TinyTroupe

This repository contains materials from **Hajime Takeda's presentation** at [PyData Global 2025](https://pydata.org/global2025).

## About This Demo

This notebook demonstrates how to use [TinyTroupe](https://github.com/microsoft/TinyTroupe) for **multi-agent persona simulation** in a product concept testing scenario.

**Use Case**: A footwear brand evaluates customer reception of three running shoe concepts across different consumer segments.

**Workflow**:
1. **Generate** diverse personas using TinyPersonFactory
2. **Simulate** 1-on-1 depth interviews with each agent
3. **Extract & Analyze** structured results

## Quick Start

### Prerequisites

```bash
pip install git+https://github.com/microsoft/TinyTroupe.git@main
pip install pandas matplotlib seaborn
```

### Setup

1. Clone this repository
2. Set your OpenAI API key:
   ```python
   import os
   os.environ["OPENAI_API_KEY"] = "your-api-key-here"
   ```
3. Open `TinyTroupe_simple_demo.ipynb` in Jupyter

### Running the Demo

The notebook is configured to **load pre-generated personas** by default (`GENERATE_NEW_PERSONAS = False`), so you can run the simulation immediately without waiting for persona generation.

To generate fresh personas, set `GENERATE_NEW_PERSONAS = True` (requires API calls).

## Repository Structure

```
.
├── TinyTroupe_simple_demo.ipynb  # Main demo notebook
├── config.ini                     # TinyTroupe configuration
├── usa.json                       # US demographics (from official repo)
├── result.csv                     # Survey results output from the notebook
└── exported_personas/             # 30 pre-generated personas (3 segments × 10)
```

**Note**: `usa.json` is sourced from the [official TinyTroupe repository](https://github.com/microsoft/TinyTroupe/blob/43d951eea015aea09972dc95537c9bbbc74ba207/publications/paper_artifacts_june-2025/information/populations/usa.json).

## Customer Segments

| Segment | Description |
|---------|-------------|
| Serious Runner | 15+ miles/week, training for races |
| Casual Jogger | 1-2 times/week for health |
| Fashion-Conscious | Style-focused, occasional exercise |

## Insights Examples from this virtual survey
The simulation reveals that segment labels don't tell the whole story:
- A 74-year-old "Serious Runner" chose cushioning (B) over lightweight (A) due to joint issues
- A CFO "Casual Jogger" chose lightweight (A) due to his optimization mindset
- A minimalist "Fashion-Conscious" shopper chose lightweight (A) for its sleek design

These insights demonstrate TinyTroupe's ability to surface **psychographic nuances** that simple demographics miss.

## Related Resources

- **TinyTroupe**: [github.com/microsoft/TinyTroupe](https://github.com/microsoft/TinyTroupe)
- **Paper**: [arxiv.org/abs/2507.09788](https://arxiv.org/abs/2507.09788)
- **PyData Global 2025**: [pydata.org/global2025](https://pydata.org/global2025)

## Questions & Collaboration
Hajime Takeda - https://www.linkedin.com/in/hajime-takeda/
