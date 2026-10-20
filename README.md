
<div align="center">

# ♠️ PokerStudio

### Your whole poker study and bankroll toolkit, in one HTML file.

Ranges · Training · Hand history · Results · Study tools

<br>

![Single file](https://img.shields.io/badge/single%20file-HTML-ec4899?style=for-the-badge)
![No install](https://img.shields.io/badge/no%20install-just%20open%20it-8b5cf6?style=for-the-badge)
![Offline data](https://img.shields.io/badge/your%20data-stays%20on%20device-10b981?style=for-the-badge)
![Mobile first](https://img.shields.io/badge/mobile-first-3b82f6?style=for-the-badge)

<br>

**[Features](#-features)** · **[Getting started](#-getting-started)** · **[Your data](#-your-data)** · **[Building from source](#%EF%B8%8F-building-from-source)**

</div>

---

## ✨ Why PokerStudio?

> **No accounts. No servers. No subscriptions.**
> Open one file on your phone or computer and start studying. Everything you save stays on your device.

<br>

## 🃏 Features

### 📚 Study

| | Tool | What it does |
|:-:|---|---|
| ♠️ | **Range Editor** | Paint preflop ranges with multiple actions and mixed frequencies. Organise them in nested folders and compare them side by side. |
| 🎯 | **Range Trainer** | Drill your ranges full screen in focus mode, with mistake drills, weak-spot and review sessions, leak drills, streaks and session history. |
| 🧮 | **Solver View** | Browse solver-style strategy for each spot. |
| 🎰 | **Best Hand Trainer** | Hold'em and Omaha (PLO4/5/6) showdowns in five training modes, with a focus mode and session summaries. |
| 🎬 | **Video Study** | Watch training videos or streams and log hands with the video time on each one. Includes folders, players, explanations, lessons and play-along predictions. |
| 🧠 | **Flowcharts** | Build decision trees on a canvas from templates and export them as PNG. |
| 📝 | **Notes** | Markdown notebooks with templates, `[[links]]`, inline playing cards and version history. |

<details>
<summary><b>🎰 The Best Hand Trainer's five modes</b></summary>

<br>

| Mode | The question |
|---|---|
| 🏆 **Showdown** | Which of 2 to 6 hands wins? Or is it a 🤝 chop? |
| ⚔️ **Win / Lose / Chop** | Your hand against one opponent. Kickers and counterfeits decide it. |
| 🏷 **Name it** | What's your best five-card hand? |
| 🥜 **Find the nuts** | Which starting hand is the nuts on this board? |
| ⏱ **Speed** | How many showdowns can you get right in 60 seconds? |

Each player's best five cards are shown in poker order, with the cards from their hand raised so you can see exactly what plays.

</details>

### 💰 Play & track

| | Tool | What it does |
|:-:|---|---|
| 💰 | **Bankroll** | Sessions, deposits and withdrawals, charts, personal records, a bankroll challenge with a start-date countdown, and a shareable card. |
| 📈 | **GG Results** | Import GGPoker hand histories to get results, luck and EV analysis, preflop range checks and hand-review prompts. |
| 📔 | **Hand History** | Two modes: **🙋 My Hands** for your own play and **📺 Study** for hands from other players or courses. Includes a fast logger, replayer, spaced-repetition review, tags and folders. |
| ⏱️ | **Shift Log** | Track work shifts alongside your poker. |

### 🛠 Tools

| 🎲 Equity | 💵 Pot Odds | 📐 SPR & Sizing | 🔢 Combos & Blockers | 🌊 Variance & Risk of Ruin |
|:-:|:-:|:-:|:-:|:-:|
| Hand and range odds | Call or fold, with a quick reference | Bet sizes and all-in plans | Blockers and bluff ratios | Swings and bankroll risk |

### 🌟 Across the whole app

- 📁 **Nested, customisable folders** with icons and colours in hands, ranges, flowcharts, notebooks and videos.
- 🎨 **Themes**, plus a theme studio for making your own.
- 🧭 **A customisable bottom bar**, global search and command shortcuts.
- 📱 **Designed for phones first**, working on desktop too, with phone back-button support.
- 🏅 **Achievements and streaks** to keep you studying.

<br>

## 🚀 Getting started

<table>
<tr>
<td width="50%" valign="top">

### 📲 Use it

1. Download **`pokerstudio.html`**.
2. Open it in any modern browser.
3. On a phone, tap **Share → Add to Home Screen** for an app-like experience.

</td>
<td width="50%" valign="top">

### 🌐 Host it on GitHub Pages

1. Add `pokerstudio.html` to the repository. Rename it **`index.html`** if you want it at the root URL.
2. Go to **Settings → Pages** and deploy from `main`.
3. Open your Pages link on any device.

</td>
</tr>
</table>

<br>

## 🔒 Your data

| | |
|:-:|---|
| 💾 | Everything is saved **in your browser**: `localStorage`, plus IndexedDB for imported GG hands. |
| 🚫 | **Nothing is uploaded.** There are no accounts and no tracking. |
| 📦 | Use **Settings → Back up all data** to keep a copy or move to another device. |
| 🧹 | Clearing your browser's site data removes your saved data, so back up first. |
| 🌍 | The only things loaded online are **Chart.js** (for charts) and web fonts. |

<br>

## 🛠️ Building from source

The app ships as one file, but it's developed as clean, modular source code.

```
src/
├── 📄 manifest.json   → the exact order every piece is joined in
├── 🧱 markup/         → page skeleton, one file per screen
├── 🎨 css/            → styles by feature
└── ⚙️ js/<area>/      → core · shell · ranges · editor · trainer · solver · analysis
                         notes · flow · gg · bankroll · challenge · charts
                         handhistory · shifts · tools · video · theme · gamification
```

```bash
python3 build.py out.html     # 🔧 assemble the single file
./make.sh <name>              # 📦 assemble + minify + release
```

<details>
<summary><b>📐 Code conventions</b></summary>

<br>

| Area | Convention |
|---|---|
| Storage | `LG(key, default)` and `LS(key, value)` read and write JSON in localStorage. |
| Sheets | `psSheet(id, title, subtitle, bodyHtml, footHtml)` |
| Feedback | `toast()`, `haptic()`, `confirmAction()` |
| Folders | `js/shell/folders.js`, plus one adapter for each area in `js/shell/folder-adapters.js` |
| Style | Prettier with a print width of 120. The release build minifies it. |

</details>

<details>
<summary><b>🏷 Releasing a new version</b></summary>

<br>

1. Bump `Build vNNN` in `markup/15-settings.html`.
2. Run `./make.sh <name>`.

</details>

<br>

---

<div align="center">

**♠️ ♥️ ♦️ ♣️**

<sub>PokerStudio is a study aid. Ranges, odds and analysis are for learning and may not be perfect. Play responsibly.</sub>

</div>
