# Effective Persona Simulation

Two approaches to **multi-agent persona simulation for product concept testing**, shown side by side so you can compare how each handles the same kinds of product-concept questions:

- [**TinyTroupe**](https://github.com/microsoft/TinyTroupe) — Microsoft's Python framework for LLM-driven persona agents. Notebook-first; bring your own OpenAI key and execute.
- [**claude-persona**](https://github.com/takechanman1228/claude-persona) — an agent-based persona research skill built on Claude Code. Natural-language commands; pre-generated results are already committed.

Originally prepared for [ODSC AI East 2026](https://odsc.com/) ([slides](https://docs.google.com/presentation/d/1Ayt_GDsPkI1AWJdWn7OgN-W0_tPgM19eMUYEHb5R7zo/edit?usp=sharing)).

## TinyTroupe demos

### 👟 Demo 1 — [Shoes Concept Test](./demo-tinytroupe/shoes/)

30 personas (3 runner segments × 10) evaluate three running-shoe concepts to uncover psychographic nuances beyond demographic labels.

→ [`demo-tinytroupe/shoes/`](./demo-tinytroupe/shoes/)

### 🧴 Demo 2 — [Gen Z Skincare Concept Test](./demo-tinytroupe/genz-skincare/)

10 Gen Z (ages 18–28) personas first answer an open-ended discovery question (*"What frustrates you most about choosing skincare products?"*), then evaluate three skincare concepts. Results are written to `discovery.csv` and `result.csv`.

→ [`demo-tinytroupe/genz-skincare/`](./demo-tinytroupe/genz-skincare/)

---

## claude-persona demos

Snapshots of [claude-persona](https://github.com/takechanman1228/claude-persona) runs on the same kinds of product concepts. Results are already committed — just browse the folders.

### 👟 Demo 3 — [Running Shoes Concept Test](./demo-claude-persona/running-shoes/)

15 AI personas rate three running-shoe concepts under the claude-persona skill (Sonnet-based).

→ [`demo-claude-persona/running-shoes/`](./demo-claude-persona/running-shoes/)

### 🧴 Demo 4 — [Gen Z Skincare Concept Test](./demo-claude-persona/genz-skincare/)

10 Gen Z personas — same three skincare concepts as Demo 2 — run through claude-persona's ask + concept-test flow.

→ [`demo-claude-persona/genz-skincare/`](./demo-claude-persona/genz-skincare/)

---

## Quick start — TinyTroupe demos

```bash
pip install git+https://github.com/microsoft/TinyTroupe.git@main
pip install pandas matplotlib seaborn jupyter

export OPENAI_API_KEY=sk-...   # export before launching Jupyter

cd demo-tinytroupe/shoes        # or demo-tinytroupe/genz-skincare
jupyter lab
```

Each TinyTroupe demo folder is **self-contained** — it has its own `config.ini`, `usa.json`, `exported_personas/`, and notebook. The claude-persona demos come with **pre-generated results already committed** — just browse the folders; no setup needed.

## Repository structure

```
.
├── README.md                           ← this file
├── .gitignore
├── demo-tinytroupe/
│   ├── shoes/                          ← Demo 1
│   │   ├── README.md
│   │   ├── TinyTroupe_shoes_demo.ipynb
│   │   ├── config.ini
│   │   ├── usa.json
│   │   ├── exported_personas/
│   │   └── result.csv
│   └── genz-skincare/                  ← Demo 2
│       ├── README.md
│       ├── TinyTroupe_genz_skincare_demo.ipynb
│       ├── config.ini
│       ├── usa.json
│       ├── exported_personas/
│       ├── discovery.csv
│       └── result.csv
├── demo-claude-persona/
│   ├── running-shoes/                  ← Demo 3
│   │   ├── README.md
│   │   ├── personas/
│   │   └── concept-test/
│   └── genz-skincare/                  ← Demo 4
│       ├── README.md
│       ├── personas/
│       ├── ask/
│       └── concept-test/
└── archive/                            ← local experiments, gitignored
```

## Related resources

- **ODSC 2026 slides**: [Google Slides]([https://docs.google.com/presentation/d/1t2fMwrQxfEMZa7Eq0JMCj2au1Tg4YPugly1MihrcxZk/edit?usp=sharing](https://docs.google.com/presentation/d/1Ayt_GDsPkI1AWJdWn7OgN-W0_tPgM19eMUYEHb5R7zo/edit?usp=sharing))
- **TinyTroupe**: [github.com/microsoft/TinyTroupe](https://github.com/microsoft/TinyTroupe)
- **Paper**: [arxiv.org/abs/2507.09788](https://arxiv.org/abs/2507.09788)

## Questions & collaboration

Hajime Takeda — [LinkedIn](https://www.linkedin.com/in/hajime-takeda/)
