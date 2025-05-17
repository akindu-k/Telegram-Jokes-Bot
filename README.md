# Telegram Jokes Bot

A Telegram bot that generates jokes on any topic using the Groq AI API and LangChain.

## Overview

This bot allows Telegram users to request jokes about specific topics. When a user mentions the bot along with a topic (e.g., `@Binary_Joke_Bot python`), the bot generates a customized joke about that topic using Groq's Gemma2-9b-It model.

## Features

- Generate jokes on any user-specified topic
- Utilizes the Groq AI API through LangChain for joke generation
- Simple mention-based interface (`@botname topic`)
- Deployed ready for Heroku (includes Procfile)

## Requirements

- Python 3.7+
- Telegram Bot API token
- Groq API key
- LangChain API key (for tracing)

## Installation

1. Clone this repository
2. Create a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
4. Create a `.env` file with the following variables:
   ```
   TELEGRAM_API_KEY=your_telegram_bot_token
   GROQ_API_KEY=your_groq_api_key
   LANGCHAIN_API_KEY=your_langchain_api_key
   LANGCHAIN_PROJECT=your_langchain_project_name
   ```

## Usage

1. Start the bot locally:
   ```
   python main.py
   ```
2. In Telegram, search for your bot username and start a conversation
3. Send a message mentioning the bot and a topic: `@BotUsername topic`
4. The bot will generate and send a joke about the specified topic

## Deployment

This bot is configured for deployment on Heroku:

1. Create a Heroku account and install the Heroku CLI
2. Login to Heroku:
   ```
   heroku login
   ```
3. Create a new Heroku app:
   ```
   heroku create your-app-name
   ```
4. Set the environment variables:
   ```
   heroku config:set TELEGRAM_API_KEY=your_telegram_token
   heroku config:set GROQ_API_KEY=your_groq_api_key
   heroku config:set LANGCHAIN_API_KEY=your_langchain_api_key
   heroku config:set LANGCHAIN_PROJECT=your_langchain_project_name
   heroku config:set LANGCHAIN_TRACING_V2=true
   ```
5. Deploy to Heroku:
   ```
   git push heroku main
   ```

## How It Works

1. The bot listens for messages that mention its username
2. When mentioned along with a topic, it extracts the topic text
3. The bot uses LangChain with the Groq API to generate a joke on that topic
4. The generated joke is sent back to the user in the Telegram chat


## Acknowledgements

- [LangChain](https://www.langchain.com/) for the AI framework
- [Groq](https://groq.com/) for the AI model API
- [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) for the Telegram API wrapper
