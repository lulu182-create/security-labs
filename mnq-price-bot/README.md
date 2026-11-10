# MNQ Price Bot

A lightweight, alert-only bot that sends MNQ (Micro E-mini Nasdaq-100 futures) price updates and a pre-market brief to Telegram. It does not place trades or connect to any brokerage/prop firm account.

## What it does
- Sends an hourly MNQ price update, Sunday through Friday
- Sends a pre-market go/no-go brief at 8:00 AM ET, flagging high-impact days (FOMC, NFP) per my trading rules
- Delivers everything via a private Telegram bot chat

## Stack
- Python
- Telegram Bot API for delivery
- Cron for scheduling
- Hosted on an Azure for Students Linux VM (North Central US)

## Design choices
- **Alert-only by design:** no order execution, no brokerage/prop firm connection. Keeps the bot out of scope for automated-trading restrictions and removes execution risk entirely.
- **Runs independent of my laptop,** on a cloud VM, so alerts continue regardless of my local setup.
- **Secrets never touch the repo:** bot token, chat ID, and any API keys are loaded from environment variables via a `.env` file, excluded via `.gitignore`.

## Basic infrastructure hardening
- SSH key-based authentication only; password login disabled
- Firewall (ufw/NSG) restricts inbound access to required ports only
- Scheduled jobs logged, with alerting if a cron job fails to run

## Setup
1. Create a Telegram bot via BotFather; note the token and chat ID.
2. Copy `.env.example` to `.env` and fill in the required values.
3. Install dependencies: `pip install -r requirements.txt`
4. Add cron entries for the hourly update and the 8:00 AM ET pre-market brief.

## Disclaimer
Built for personal use and education. Not financial advice.
