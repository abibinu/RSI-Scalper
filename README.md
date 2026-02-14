<div align="center">

# 📊 Forex RSI Mean Reversion Scalping Bot

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Platform MT5](https://img.shields.io/badge/Platform-MetaTrader%205-orange.svg)](https://www.mql5.com/en/terminal)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Market EURUSD](https://img.shields.io/badge/Market-EURUSD-blue)](https://www.google.com/finance/quote/EUR-USD)

**A concise, production-ready RSI-based mean-reversion scalping bot for EUR/USD on MetaTrader 5.**

</div>

---

## 🚀 Overview
This repository provides a complete automated trading solution, including logic for MT5 connectivity, risk management, and utility functions. It is designed to exploit overbought and oversold conditions using a mean-reversion strategy.

### 📋 Quick Facts
| Feature | Details |
| :--- | :--- |
| **Strategy** | 9-period RSI Mean-Reversion |
| **Thresholds** | Extreme RSI levels (25 / 75) |
| **Timeframe** | M5 (5-Minute Candles) |
| **Asset** | EURUSD |
| **TP / SL** | 15 Pips / 8 Pips (Configurable) |

---

## ✨ Key Highlights
- 🤖 **Automated Execution:** Seamless integration with MetaTrader 5 Python API.
- 🕒 **Smart Filtering:** Built-in spread and session filtering (defaults to IST hours).
- ⚖️ **Risk Management:** Dynamic position sizing and daily loss limits.
- 📝 **Developer Friendly:** Clear logging and simple configuration structure.

---

## 💻 Requirements
Before you begin, ensure you have the following:
- **Python 3.8+**
- **MetaTrader 5 Terminal:** Installed and logged in (IC Markets or similar broker).
- **Network:** Stable internet connection (VPS recommended for 24/7 operation).

### 📦 Python Dependencies
Install via `requirements.txt`:
- `MetaTrader5`
- `pandas`
- `numpy`
- `ta-lib`
- `python-dotenv`

---

## 🛠 Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-repo/forex-rsi-bot.git
   cd forex-rsi-bot
   ```

2. **Initialize Virtual Environment**
   ```bash
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # macOS / Linux:
   source venv/bin/activate
   ```

3. **Install Packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Configuration**
   Create a `.env` file in the project root:
   ```env
   MT5_LOGIN=your_account_number
   MT5_PASSWORD=your_password
   MT5_SERVER=ICMarketsSC-Demo
   ```

---

## ⚙️ Configuration
<details>
<summary>Click to view configuration parameters</summary>

Edit `config.py` to adjust core parameters:

```python
SYMBOL = "EURUSD"
TIMEFRAME = mt5.TIMEFRAME_M5
LOT_SIZE = 0.01
RSI_PERIOD = 9
RSI_OVERSOLD = 25
RSI_OVERBOUGHT = 75
STOP_LOSS_PIPS = 8
TAKE_PROFIT_PIPS = 15
MAX_SPREAD_PIPS = 1.5
TRADING_START_HOUR = 12   # IST
TRADING_END_HOUR = 21     # IST
```
</details>

---

## 🏃 Running the Bot
Ensure your MetaTrader 5 terminal is running and logged in, then execute:

```bash
python main.py
```
*The bot will automatically connect to MT5, fetch recent candle data, and begin monitoring for signals.*

---

## 📂 Project Structure
<details>
<summary>Expand project layout</summary>

```text
.
├── main.py            # Main entry point / launcher
├── config.py          # Strategy and risk parameters
├── src/               # Core business logic
│   ├── mt5_connector  # MT5 API interface
│   ├── strategy       # RSI logic
│   ├── risk_manager   # Sizing and limits
│   └── order_manager  # Trade execution
├── utils/             # Helper functions (logger, indicators)
└── logs/              # Runtime log files
```
</details>

---

## ⚠️ Safety & Testing
> [!IMPORTANT]
> **Always test thoroughly before risking real capital.**

- **Demo Testing:** Run on a demo account for at least 60 days.
- **Risk Control:** Start with the smallest lot size (0.01) and limit risk per trade (e.g., 1–1.5% equity).
- **News Events:** Avoid trading during major economic news releases.
- **Disclaimer:** This software is for educational purposes. Trading involves significant risk of loss.

---

## 🤝 Contributing
Contributions are welcome!
- Follow [PEP 8](https://peps.python.org/pep-0008/) style guidelines.
- Add tests for new features.
- Open a Pull Request with a clear description of changes.

---

## 📜 License
Distributed under the **MIT License**. See `LICENSE` for more information.

---
<div align="center">
  <sub>Last updated: February 2026</sub>
</div>
