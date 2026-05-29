# ChainX — Reputation-Driven Supply Chain with Self-Evolving Trust Graph

![HTML](https://img.shields.io/badge/HTML%2FJS%2FCSS-Zero%20Dependencies-e34c26?style=flat-square)
![Live](https://img.shields.io/badge/Live-GitHub%20Pages-00dcc8?style=flat-square)
![Version](https://img.shields.io/badge/version-1.0.0-blue?style=flat-square)

A supply chain intelligence dashboard where every shipment shapes a stakeholder's **trust score** in real-time. Built as a zero-dependency, pure-frontend system — open `index.html` in any browser and it runs.

> **Live demo:** [itsmilindsahu.github.io/ChainX](https://itsmilindsahu.github.io/ChainX/)

---

## Concept

Traditional supply chain tools track logistics. ChainX tracks **trust**. Each stakeholder (supplier, transporter, warehouse, retailer) has a reputation score that updates dynamically based on shipment outcomes, delivery conditions, quality ratings, and fraud flags — surfacing the best partners and flagging unreliable ones before problems escalate.

---

## System Design

```
Shipment Event (form input)
        │
        ▼
┌─────────────────────────────────────────┐
│         Trust Score Engine (JS)          │
│                                          │
│  Δ score = f(outcome, condition,         │
│             rating, flags, lateness)     │
│                                          │
│  Rules:                                  │
│  • Delivered on-time, good condition:   │
│    +weight                               │
│  • Late / damaged / flagged:            │
│    −weight (severity-scaled)            │
│  • Score clamped [0, 100]               │
│  • Exponential moving average smoothing │
└──────────────────┬──────────────────────┘
                   │  updated scores
                   ▼
┌─────────────────────────────────────────┐
│      Force-Directed Trust Graph          │
│  (D3.js / vanilla Canvas)               │
│                                          │
│  • Nodes = stakeholders                 │
│  • Node size ∝ trust score              │
│  • Node color:                          │
│    green (>70) / amber (40–70) /        │
│    red (<40)                            │
│  • Edges = active supply relationships  │
│  • Edge weight ∝ shipment volume        │
└──────────────────┬──────────────────────┘
                   │
                   ▼
┌─────────────────────────────────────────┐
│      Smart Recommendation Engine        │
│  Rule-based partner suggestions:        │
│  • Best supplier by category            │
│  • Flag high-risk links                 │
│  • Surface underused high-trust nodes   │
└─────────────────────────────────────────┘
```

---

## Features

| Feature | Implementation |
|---|---|
| Dynamic trust scoring | JS scoring engine with configurable weights |
| Live trust graph | Force-directed network, nodes sized & coloured by score |
| Shipment simulator | Full form: outcome, condition, rating, flags |
| Smart recommendations | Rule-based best-partner surfacing from live graph data |
| Stakeholder drawer | Per-node history, score timeline, shipment log |
| Zero dependencies | Pure HTML/CSS/JS — no build step, no npm |

---

## Files

```
ChainX/
├── index.html   ← Landing page
└── app.html     ← Main dashboard (trust graph + simulator + recommendations)
```

---

## Running Locally

```bash
# No install needed — just open in browser
open index.html
# or
python -m http.server 8080
```
