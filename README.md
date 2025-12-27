# 369

![Pine Script](https://img.shields.io/badge/Pine%20Script-v6-blue.svg) ![Platform](https://img.shields.io/badge/Platform-TradingView-green.svg)

**369** is a specialized scalping indicator for **TradingView** designed for the **1-minute timeframe**. It combines classic market structure (Swing Highs/Lows) with Tesla's 3-6-9 numerology theory to filter trade signals based on time alignment.

## 🚀 Features

* **Fractal Swing Detection:** Identifies local market tops and bottoms automatically.
* **3-6-9 Time Filter:** Validates swings using "Digital Root" mathematics applied to the specific candle time.
* **Auto-Cleanup:** Automatically removes old labels after **10 minutes** (configurable) to keep the chart clean and improve performance.
* **Smart Label Positioning:** Prevents overlap between time labels and number labels using dynamic styling.
* **Debug Mode:** Optional feature to reveal "hidden" swings (non-369) for backtesting and verification.
* **Timezone Support:** Customizable timezone input (default UTC+5) for accurate calculation regardless of exchange time.

---

## 🧠 How It Works

The indicator follows a strict priority logic to calculate the "Digital Root" (reducing sums to a single digit) of the candle's timestamp.

### 1. Swing Detection
It first waits for a confirmed Swing High or Swing Low (Fractal pattern).
* *Note: Signals appear after the confirmation candle closes (1-candle lag).*

### 2. The 369 Logic
Once a swing is found, it checks the time:

| Priority | Check | Logic | Example |
| :--- | :--- | :--- | :--- |
| **1st** | **Minute Only** | Sum the digits of the minute. If the result is **3, 6, or 9**, the signal is **VALID**. | `18:45` <br> $4+5 = 9$ (Pass) ✅ |
| **2nd** | **Total Sum** | If Priority 1 fails, sum (Hour + Minute). If the result is **3, 6, or 9**, the signal is **VALID**. | `10:14` <br> Min: $1+4=5$ (Fail) <br> Hour: $1+0=1$ <br> Total: $1+5=6$ (Pass) ✅ |
| **Result** | **Invalid** | If neither calculation results in 3, 6, or 9. | `18:28` <br> Result = 1. (Hidden) ❌ |

---

## ⚙️ Configuration

### Appearance
* **Time Text Color:** Color for the timestamp (e.g., `18:30`).
* **Number 3-6-9 Color:** Color for the valid signal number.

### Settings
* **Show Last (Minutes):** *Default: 10*. Determines how long signals remain on the chart.
    * *Example:* On a 1m chart, labels older than 10 candles will be auto-deleted.
* **Timezone:** *Default: UTC+5*. Adjust this string (e.g., `UTC-5`, `GMT+7`) to match your preferred trading hours.

### Debugging
* **Show Non-369 Swings (Gray):** Enable this to see swings that were filtered out. They will appear in **Gray**. This is useful to verify that the swing detection is working even when the math condition isn't met.

---

## 📖 Visual Legend

| Position | Signal Type | Label Style |
| :--- | :--- | :--- |
| **Above Bar** | **Swing High** (Sell) | Time is centered. Number has an **arrow pointing down**. |
| **Below Bar** | **Swing Low** (Buy) | Time is centered. Number has an **arrow pointing up**. |

---

## 📦 Installation

1.  Open **TradingView**.
2.  Go to **Pine Editor** tab at the bottom.
3.  Create a new indicator and paste the source code.
4.  Click **Save** and **Add to Chart**.

---

## ⚠️ Disclaimer

> This tool is for educational and assistive purposes only. Past performance based on numerology alignment does not guarantee future price action. Always use proper risk management.

<img width="1817" height="745" alt="image" src="https://github.com/user-attachments/assets/22d0c5d8-aba6-4725-9530-1d6065f7c9d5" />
