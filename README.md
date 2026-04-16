# Axiom Labs — Trust-Driven Supply Chain Platform

> A reputation-first supply chain intelligence dashboard. Every shipment shapes a stakeholder's trust score — live, transparent, and actionable.

![Axiom Labs](https://img.shields.io/badge/Axiom%20Labs-v1.0.0-00dcc8?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-Pure%20Frontend-e34c26?style=for-the-badge)
![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-2ecc71?style=for-the-badge)

---

## 🚀 Live Demo

Open `index.html` in any browser — no server, no install, no dependencies.

---

## 📁 File Structure

```
axiom-labs/
├── index.html        ← Landing page (start here)
├── app.html          ← Main application (dashboard + graph + simulator)
└── README.md
```

---

## ✨ Features

| Feature | Description |
|---|---|
| **Dynamic Reputation** | Trust scores update instantly on every simulated shipment |
| **Live Trust Graph** | Force-directed network graph — nodes sized & colored by score |
| **Shipment Simulator** | Full form with outcome, condition, rating, flags → score recalculation |
| **Smart Recommendations** | Rule-based best partner suggestions surfaced from live data |
| **Stakeholder Drawer** | Click any node or card to see full stakeholder profile |
| **Toast + Flash** | Visual feedback on every score change (green/red flash, toast notification) |

---

## 🖥️ Pages

### Landing Page (`index.html`)
- Hero with animated tagline
- Feature highlights
- Live dashboard mockup preview
- "Why Axiom Labs" comparison section
- Footer with nav links

### App (`app.html`)
Three views accessible from the sidebar:

1. **Dashboard** — KPI summary cards, stakeholder grid, recent shipments table, top/watchlist panels, recommendations
2. **Trust Graph** — Interactive canvas force-directed graph; click any node to open detail drawer
3. **Simulate** — Full shipment simulation form with live result panel

---

## 🧮 Reputation Logic

```
Base Score: 50

Delivery:
  On Time      → +5
  Delayed      → -5
  Major Delay  → -10
  Disputed     → -15

Condition:
  Damaged      → -10

Rating:
  4 or 5 stars → +3
  1 or 2 stars → -3

False Data:   → -20

Bonus (On Time + Good + Rating 5) → +2

Range: 0 – 100
```

**Badge Thresholds:**
- 🟢 `85+` → **Trusted**
- 🔵 `65–84` → **Rising**
- 🟡 `40–64` → **Watchlist**
- 🔴 `<40` → **Critical**

---

## 🎯 Demo Scenarios

### Scenario 1 — Good Transaction
1. Go to **Simulate**
2. Sender: `Nexus Logistics`, Receiver: `Orion Retail`
3. Status: On Time · Condition: Good · Rating: 5★
4. Hit **Simulate Shipment** → score increases, badge may upgrade

### Scenario 2 — Delayed Shipment
1. Sender: `ArcMfg Co.`, Receiver: `SwiftShip`
2. Status: Delayed · Rating: 2★ · Delay Hours: 12
3. Score drops, stakeholder may enter Watchlist

### Scenario 3 — Fraud Behavior
1. Sender: `GreenSource`, any Receiver
2. Status: Disputed · False Data: Yes · Rating: 1★
3. Maximum penalty — node turns red, removed from recommendations

---

## 🛠️ Tech Stack

- **Pure HTML/CSS/JS** — zero build tools, zero dependencies
- **Canvas API** — trust graph rendered with force-directed simulation
- **Google Fonts** — Syne (display) + DM Mono (data) + Outfit (body)
- **In-memory state** — all data lives in a JS object, updates propagate instantly

---

## 📦 Deploy to GitHub Pages

1. Push both files to a GitHub repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your site will be live at `https://<username>.github.io/<repo>/`

---

## 🏗️ Local Usage

```bash
# Option 1: Just open directly
open index.html

# Option 2: Serve locally (optional, for strict CORS environments)
npx serve .
# or
python3 -m http.server 8080
```

---

Built with purpose. Reputation is the new currency of supply chains.
