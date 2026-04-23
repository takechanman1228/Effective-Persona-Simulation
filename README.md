# Effective Persona Simulation with TinyTroupe

Two [TinyTroupe](https://github.com/microsoft/TinyTroupe) demo notebooks exploring **multi-agent persona simulation for product concept testing**. Originally prepared for [PyData Global 2025](https://pydata.org/global2025) ([slides](https://docs.google.com/presentation/d/1t2fMwrQxfEMZa7Eq0JMCj2au1Tg4YPugly1MihrcxZk/edit?usp=sharing)).

## 👟 Demo 1 — [Shoes Concept Test](./demo-tinytroupe/shoes/)

30 personas (3 runner segments × 10) evaluate three running-shoe concepts to uncover psychographic nuances beyond demographic labels.

→ [`demo-tinytroupe/shoes/`](./demo-tinytroupe/shoes/)

## 🧴 Demo 2 — [Gen Z Skincare Concept Test](./demo-tinytroupe/genz-skincare/)

10 Gen Z (ages 18–28) personas first answer an open-ended discovery question (*"What frustrates you most about choosing skincare products?"*), then evaluate three skincare concepts. Results are written to `discovery.csv` and `result.csv`.

→ [`demo-tinytroupe/genz-skincare/`](./demo-tinytroupe/genz-skincare/)

---

## Also showcased — claude-persona

[claude-persona](https://github.com/takechanman1228/claude-persona) is an agent-based persona research skill built in parallel with this TinyTroupe exploration. The two demos below are snapshots of the claude-persona runs on the same kinds of product concepts, included here so conference attendees can compare the two engines side by side.

### 👟 Demo 3 — [claude-persona Running Shoes](./demo-claude-persona/running-shoes/)

15 AI personas rate three running-shoe concepts under the claude-persona skill (Sonnet-based).

→ [`demo-claude-persona/running-shoes/`](./demo-claude-persona/running-shoes/)

### 🧴 Demo 4 — [claude-persona Gen Z Skincare](./demo-claude-persona/genz-skincare/)

10 Gen Z personas — same three skincare concepts as Demo 2 — run through claude-persona's ask + concept-test flow.

→ [`demo-claude-persona/genz-skincare/`](./demo-claude-persona/genz-skincare/)

---

## Quick start (TinyTroupe demos)

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

- **PyData Global 2025 slides**: [Google Slides](https://docs.google.com/presentation/d/1t2fMwrQxfEMZa7Eq0JMCj2au1Tg4YPugly1MihrcxZk/edit?usp=sharing)
- **TinyTroupe**: [github.com/microsoft/TinyTroupe](https://github.com/microsoft/TinyTroupe)
- **Paper**: [arxiv.org/abs/2507.09788](https://arxiv.org/abs/2507.09788)

## Questions & collaboration

Hajime Takeda — [LinkedIn](https://www.linkedin.com/in/hajime-takeda/)
