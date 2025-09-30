# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python script that provides trading advice based on Twitter news from influential people. The project is in early stages with minimal implementation.

## Project Setup

- **Python Version**: 3.13+
- **Package Manager**: UV (modern Python package manager)
- **Virtual Environment**: `.venv/` (managed by uv)

## Commands

### Running the Application
```bash
uv run main.py
```

### Adding Dependencies
```bash
uv add <package-name>
```

### Installing Dependencies
```bash
uv sync
```

### Running with VS Code Task
The default build task is configured to run `uv run main.py` (Cmd/Ctrl+Shift+B)

## Architecture

The codebase is currently minimal with a single `main.py` entry point. As the project develops:
- The main functionality will involve fetching Twitter data from influential accounts
- Processing and analyzing news content
- Generating trading advice based on the analyzed information


future project structure (draft):
news-trading/
  ├── news_trading/              # Main package
  │   ├── __init__.py
  │   ├── twitter/
  │   │   ├── __init__.py
  │   │   ├── client.py
  │   │   └── models.py
  │   ├── analysis/
  │   │   ├── __init__.py
  │   │   ├── openai_client.py
  │   │   └── prompts.py
  │   ├── notification/
  │   │   ├── __init__.py
  │   │   └── telegram.py
  │   ├── storage/
  │   │   ├── __init__.py
  │   │   └── db.py
  │   └── config.py
  ├── tests/                     # Test directory
  │   ├── __init__.py
  │   ├── test_twitter.py
  │   ├── test_analysis.py
  │   └── test_notification.py
  ├── data/                      # Runtime data (gitignored)
  │   └── .gitkeep
  ├── config/                    # User configuration files
  │   ├── watchlist.yaml         # Accounts/keywords to monitor
  │   └── settings.yaml.example  # Template for settings
  ├── main.py                    # Entry point
  ├── .env.example               # API keys template
  ├── .gitignore
  ├── pyproject.toml             # uv/pip dependencies & project 
  metadata
  ├── README.md
  └── LICENSE