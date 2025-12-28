# SilentOp 🦅

![Pine Script](https://img.shields.io/badge/Pine%20Script-v6-blue.svg) ![Platform](https://img.shields.io/badge/Platform-TradingView-green.svg) ![Type](https://img.shields.io/badge/Type-Scalping-orange)

**SilentOp** is a specialized precision scalping indicator for **TradingView**, optimized for the **1-minute (M1) timeframe**. It seamlessly combines **Tesla's 3-6-9 Numerology** swing trading logic with advanced **New Week Open Gap (NWOG)** structure analysis.

## 🌟 Key Features

### 1. 3-6-9 Swing Detection
* **Fractal Identification:** Automatically detects Swing Highs and Swing Lows based on market structure.
* **Numerology Filter:** Filters swings using "Digital Root" mathematics. A signal is valid only if the time aligns with the vibration of **3, 6, or 9**.
* **Smart Priority Logic:** Uses a 3-step summation algorithm to capture valid signals that standard summation might miss (e.g., *12:25* becomes valid via specific unit summation).
* **Auto-Cleanup:** Automatically removes old signals after a configurable time (default: 10 mins) to keep the chart clean and focused.

### 2. Advanced NWOG (New Week Open Gap)
* **5-Week History:** Displays New Week Open Gaps for the current week and the 4 previous weeks.
* **Force Load Data:** Uses `request.security` to ensure gaps are visible even on the M1 timeframe where historical data might not fully load.
* **CE (Consequent Encroachment):** Optional 50% median line (Center Line) for each gap with fully customizable styles.
* **Dual-Anchor Labels (Smart Visibility):**
    * **Anchor A (History):** Fixed at the start of the week (allows you to see gap details while backtesting).
    * **Anchor B (Real-time):** Floats on the right side of the current price (allows you to see all 5 gaps simultaneously while trading live).
* **Horizontal Ray:** Lines extend infinitely to the right.

---

## 🧠 How It Works

### The 3-6-9 Logic
SilentOp calculates the **Digital Root** (sum of digits reduced to a single number) of the candle's timestamp.

| Priority | Calculation | Condition |
| :--- | :--- | :--- |
| **1. Minute** | Sum of Minute digits. | If **3, 6, 9** → **VALID** ✅ |
| **2. Min + Hour(Unit)** | Sum of (Minute + Hour's last digit). | If **3, 6, 9** → **VALID** ✅ |
| **3. Min + Hour(Total)**| Sum of (Minute + Hour's last digit + Hour's first digit). | If **3, 6, 9** → **VALID** ✅ |

### The NWOG Logic
* **Definition:** The gap between the Previous Week's Close (Friday) and the Current Week's Open (Monday).
* **CE 50%:** The midpoint of the gap, acting as a key institutional reference level.
* **Visuals:** Draws horizontal rays for the Top, Bottom, and CE of the gap. Labels are placed at both the origin and the current price level.

---

## ⚙️ Configuration

### 369 Settings
* **Enable 369:** Toggle the swing detection on/off.
* **Colors:** Customize the Time text and Number text colors.
* **Keep Signals (Minutes):** Duration signals remain on the chart (Default: 10).
* **Timezone:** Adjust to your exchange's timezone (Default: `UTC+5`).

### NWOG Settings
* **Enable NWOG:** Toggle the gap lines on/off.
* **Colors:** Customize Line and Text colors independently.
* **Show CE (50%):** Toggle the dashed centerline.
    * *CE Style:* Customize color, width, and style (Solid/Dashed/Dotted).

---

## 📸 Screenshots

*(Upload your screenshots to an 'images' folder and link them here)*
---

## 📦 Installation

1.  Open **TradingView**.
2.  Go to the **Pine Editor** tab at the bottom.
3.  Create a new indicator.
4.  Copy & Paste the source code.
5.  Click **Save** and **Add to Chart**.

---

## ⚠️ Disclaimer

> **SilentOp** is for educational and assistive purposes only. Past performance based on numerology alignment or gap fills does not guarantee future price action. Always use proper risk management.

---

**© Guaryka**
