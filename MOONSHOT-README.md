# 🚀 MOONSHOT — Crypto Crash Game

A browser-based multiplier crash game inspired by crypto gambling mechanics. Built with pure HTML, CSS, and vanilla JavaScript — no frameworks, no dependencies.

![Game Preview](https://img.shields.io/badge/status-playable-00ff88?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-pure-orange?style=for-the-badge&logo=html5)
![CSS](https://img.shields.io/badge/CSS-vanilla-blue?style=for-the-badge&logo=css3)
![JS](https://img.shields.io/badge/JS-vanilla-yellow?style=for-the-badge&logo=javascript)

---

## 🎮 How to Play

1. **Wait** for the betting phase (3 seconds before each round)
2. **Enter** your bet amount and click **PLACE BET**
3. Watch the multiplier climb: `1.00×` → `2×` → `5×` → `20×` → ...
4. **Click CASH OUT** before the chart crashes
5. If you cash out in time → you win `bet × multiplier`
6. If the game crashes before you cash out → you lose your bet

---

## ✨ Features

- **Real-time chart** — live exponential curve rendered on Canvas, with logarithmic Y-axis scaling
- **Auto Cash Out** — set a target multiplier and the game cashes out automatically when reached
- **Quick Bet buttons** — $10 / $25 / $50 / $100 presets
- **Round history** — color-coded win/loss log for the last 20 rounds
- **Live statistics** — Wins, Losses, Net Profit tracked per session
- **Bet queueing** — place a bet during an active round and it auto-triggers next round
- **Neon space aesthetic** — animated starfield, glowing text, crash shake animation
- **Responsive layout** — works on desktop and mobile

---

## 🧮 Crash Math

The crash point is generated using a provably-fair-inspired formula:

```js
// 5% instant crash probability
if (Math.random() < 0.05) return 1.0 + Math.random() * 0.1;

// Fat-tail distribution (house edge ~5%)
const e = 0.05;
const crash = 1 / (1 - r * (1 - e));
```

The multiplier grows exponentially during the round:

```js
multiplier = e^(0.12 * elapsed_seconds)
```

---

## 📁 Project Structure

```
moonshot/
└── index.html      # Single-file game — everything included
```

No build step. No npm install. Just open `index.html` in a browser.

---

## 🚀 Getting Started

```bash
git clone https://github.com/yourusername/moonshot.git
cd moonshot
# Open in browser
open index.html
```

Or simply drag `index.html` into any modern browser.

---

## 🎨 Tech Stack

| Layer      | Technology                        |
|------------|-----------------------------------|
| Rendering  | HTML5 Canvas (2D)                 |
| Styling    | Pure CSS (custom properties, keyframes) |
| Logic      | Vanilla JavaScript (RAF loop)     |
| Fonts      | Google Fonts — Bebas Neue, Rajdhani, Space Mono |

---

## ⚙️ Configuration

You can tweak these constants at the top of the `<script>` block:

| Constant       | Default | Description                          |
|----------------|---------|--------------------------------------|
| `balance`      | `1000`  | Starting balance ($)                 |
| `rate`         | `0.12`  | Multiplier growth rate (per second)  |
| `e` (house edge) | `0.05` | House edge for crash distribution   |
| `MAX_CHART_POINTS` | `300` | Max data points on canvas          |

---

## 📸 Preview

```
┌─────────────────────────────────────────────┐
│  MOONSHOT          Balance: $1,000.00        │
├─────────────────────────────────────────────┤
│                                              │
│        3.47×  🚀                            │
│       LIVE                                   │
│                                              │
│  [Real-time exponential chart]               │
│                                              │
│  🟢 Round in progress...                    │
├──────────────┬──────────────────────────────┤
│  Place Bet   │  Round History               │
│  [$ Input ]  │  3.47×  +$42.00             │
│  CASH OUT    │  1.02×  -$25.00             │
│  $173.50     │  8.11×  +$100.00            │
└──────────────┴──────────────────────────────┘
```

---

## ⚠️ Disclaimer

This is a **simulation game** for entertainment purposes only. No real money is involved. The mechanics are inspired by crash gambling games but this project is purely educational/recreational.

---

## 📄 License

MIT License — free to use, modify, and distribute.
