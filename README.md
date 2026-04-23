# Effective Persona Simulation with TinyTroupe

Two [TinyTroupe](https://github.com/microsoft/TinyTroupe) demo notebooks exploring **multi-agent persona simulation for product concept testing**. Originally prepared for [PyData Global 2025](https://pydata.org/global2025) ([slides](https://docs.google.com/presentation/d/1t2fMwrQxfEMZa7Eq0JMCj2au1Tg4YPugly1MihrcxZk/edit?usp=sharing)).

## 👟 Demo 1 — [Shoes Concept Test](./demos/shoes/)

30 personas (3 runner segments × 10) evaluate three running-shoe concepts to uncover psychographic nuances beyond demographic labels.

→ [`demos/shoes/`](./demos/shoes/)

## 🧴 Demo 2 — [Gen Z Skincare Concept Test](./demos/genz-skincare/)

10 Gen Z (ages 18–28) personas evaluate three skincare concepts. Each persona explains its choice, rates purchase likelihood, and suggests one improvement; results are written to `result.csv`.

→ [`demos/genz-skincare/`](./demos/genz-skincare/)

---

## Quick start

```bash
pip install git+https://github.com/microsoft/TinyTroupe.git@main
pip install pandas matplotlib seaborn jupyter

export OPENAI_API_KEY=sk-...   # export before launching Jupyter

cd demos/shoes        # or demos/genz-skincare
jupyter lab
```

Each demo folder is **self-contained** — it has its own `config.ini`, `usa.json`, `exported_personas/`, and notebook. No parent-path juggling needed.

## Repository structure

```
.
├── README.md                  ← this file
├── .gitignore
├── demos/
│   ├── shoes/                 ← Demo 1
│   │   ├── README.md
│   │   ├── TinyTroupe_shoes_demo.ipynb
│   │   ├── config.ini
│   │   ├── usa.json
│   │   ├── exported_personas/
│   │   └── result.csv
│   └── genz-skincare/         ← Demo 2
│       ├── README.md
│       ├── TinyTroupe_genz_skincare_demo.ipynb
│       ├── config.ini
│       ├── usa.json
│       └── result.csv
└── archive/                   ← local experiments, gitignored
```

## Related resources

- **PyData Global 2025 slides**: [Google Slides](https://docs.google.com/presentation/d/1t2fMwrQxfEMZa7Eq0JMCj2au1Tg4YPugly1MihrcxZk/edit?usp=sharing)
- **TinyTroupe**: [github.com/microsoft/TinyTroupe](https://github.com/microsoft/TinyTroupe)
- **Paper**: [arxiv.org/abs/2507.09788](https://arxiv.org/abs/2507.09788)

## Questions & collaboration

Hajime Takeda — [LinkedIn](https://www.linkedin.com/in/hajime-takeda/)
