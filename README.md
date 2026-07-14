# 🎰 Roulette Repeater Strategy Tracker

A lightweight, single-file static web app to track roulette spins and identify **repeating numbers** in real time — a digital alternative to a spreadsheet for players using the Repeater Strategy.

---

## What It Does

After each spin you manually enter the result. The tracker automatically:

- Detects when a number **repeats** (appears again after previously being spun)
- Marks the **current unique streak** with a `←` arrow, starting from the point where the last repeater first appeared
- Displays a live **"Since Repeater"** counter showing how many numbers are in the active unique streak
- Colors each spin cell with the correct **roulette wheel color** — red, black, or green (0)
- Highlights the **repeater cell** with a gold ring so it stands out from regular red numbers

---

## Features

| Feature | Details |
|---|---|
| 🔴⚫🟢 **Slot Colors** | Every entered number is colored to match the actual roulette wheel (red / black / green) |
| `←` **Arrow Markers** | Arrows appear on all numbers in the current unique streak — starting from right after where the last repeater first appeared |
| 📊 **Since Repeater Counter** | Live count of numbers in the active unique streak; resets and recounts on each new repeat |
| 💛 **Repeater Ring** | Repeating numbers get a gold inset border on top of their slot color, keeping them visually distinct |
| 📝 **Two Note Columns** | Free-text fields on every row for personal annotations (e.g. W / L / bet size) |
| ➕ **Add Row** | Add more rows at any time; pressing Enter on the last row auto-adds the next |
| ⌨️ **Keyboard Navigation** | Navigate rows with Enter / ↑ / ↓ arrow keys |
| 💾 **Auto-Save** | All spins and notes are saved to `localStorage` — data survives page refresh |
| ↺ **Reset Button** | One-click reset with a confirmation dialog to prevent accidental data loss |

---

## How the Streak Logic Works

Given the spin sequence: `24 → 7 → 15 → 18 → 5 → 15 → 6 → 23 → 31`

1. Numbers are tracked in order. When **15** appears a second time, it is flagged as a **repeater**.
2. The app looks back and finds that **15** first appeared at position 3 (index 2).
3. The **unique streak** is defined as everything from position 4 onward (right after where 15 first appeared): `18, 5, 15★, 6, 23, 31`
4. Arrows appear on all of those numbers; **Since Repeater** shows **6**.

This mirrors the "Mister Rafael's Repeater Strategy" tracking method, where you monitor how long the current unique run has been going since the last repeat cycle began.

---

## Usage

1. **Download** or clone the repo
2. Open `index.html` directly in any modern browser — no server or build step needed
3. Click the first **Spins** cell and type a number (0–36)
4. Press **Enter** or **↓** to move to the next row
5. Watch the tracker auto-detect repeaters and update the counter

---

## Tech Stack

- **HTML5** — semantic structure
- **Vanilla CSS** — custom dark theme with CSS variables, glassmorphism, and micro-animations
- **Vanilla JavaScript** — zero dependencies, no frameworks
- **localStorage** — persistent state across sessions
- **Google Fonts** — Oswald + Inter

---

## License

MIT — free to use, modify, and share.
