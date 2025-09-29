# BinanceBot

## Purpose
Automated Telegram bot for Binance futures trading that processes trading signals and executes trades for multiple users simultaneously.

## Flow
1. Bot receives trading signals via Telegram channel
2. Parses signal data (pair, side, TP, SL)
3. Executes trades for all active users with API keys
4. Monitors positions and closes on TP/SL hits
5. Tracks user trades and PnL in database

## Structure
```
BinanceBot/
├── bot.py                 # Main Telegram bot handler
├── config.py             # Bot configuration
├── create_tables.py      # Database initialization
├── requirements.txt      # Dependencies
├── database/
│   ├── db.py            # Database connection
│   ├── models.py        # SQLAlchemy models
│   ├── trades_services.py # Trade operations
│   └── user_services.py  # User management
├── handlers/
│   └── signal_message.py # Signal processing
├── keyboards/
│   └── api_keys.py      # Telegram keyboards
└── trading_bot/
    ├── bot_file.py      # Binance trading logic
    ├── trade_check.py   # Position monitoring
    └── websocket_cl.py  # WebSocket connection
```

## Language
Python

## Tools
- **aiogram** - Telegram Bot API
- **python-binance** - Binance API client
- **SQLAlchemy** - Database ORM
- **websocket-client** - Real-time data
- **telethon** - Telegram client
