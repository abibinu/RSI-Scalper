Forex RSI Mean Reversion Scalping Bot

 

A concise, production-ready implementation of an RSI-based mean-reversion scalping bot for EUR/USD on MetaTrader 5. The repository contains the trading logic, MT5 connectivity, risk manager, and utilities needed to run and test the strategy.


---

Quick facts

Strategy: 9-period RSI mean-reversion (extreme thresholds: 25/75)

Timeframe: M5 (5-minute candles)

TP / SL: 15 pips / 8 pips (configurable)

Primary pair: EURUSD

Platform: MetaTrader 5 (MT5 Python API)



---

Highlights

MT5 integration and automated execution

Spread and session filtering (IST hours by default)

Dynamic position sizing & daily loss limits

Clear logging and simple configuration



---

Requirements

Python 3.8+

MT5 terminal installed and logged in (IC Markets or similar broker)

Stable internet (VPS recommended for 24/7 run)


Python packages (install via requirements.txt):

MetaTrader5
pandas
numpy
ta-lib
python-dotenv


---

Installation & setup

1. Clone the repo:



git clone https://github.com/yourusername/forex-rsi-scalping-bot.git
cd forex-rsi-scalping-bot

2. Create and activate a virtual environment:



python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

3. Install dependencies:



pip install -r requirements.txt

4. Create a .env in project root with your MT5 credentials:



MT5_LOGIN=your_account_number
MT5_PASSWORD=your_password
MT5_SERVER=ICMarketsSC-Demo


---

Configuration

Edit config.py to change core parameters. Key options:

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


---

Run

Ensure MT5 terminal is running and logged in, then:

python main.py

The bot will connect to MT5, load recent candles, and begin monitoring for signals.


---

Project layout (short)

main.py            # launcher
config.py          # strategy & risk params
src/               # core modules: mt5_connector, strategy, risk_manager, order_manager
utils/             # logger, indicators
logs/              # runtime logs


---

Safety & testing (must-read)

Demo-test ≥ 60 days before live trading.

Start with the smallest lot (0.01) and limit risk per trade (e.g., 1–1.5% equity).

Never trade during major news events. Monitor spread and slippage.

This software is for educational purposes — trading involves risk.



---

Contributing

Contributions welcome. Please follow PEP8, add tests for new features, and open a PR with a clear description.


---

License

MIT — see the LICENSE file.


---

Last updated: February 2026
