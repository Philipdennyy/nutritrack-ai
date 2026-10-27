# nutritrack-ai
# NutriTrack AI – AI-Powered Nutrition Tracking Chatbot

## Overview

NutriTrack AI is an AI-powered nutrition tracking chatbot that helps users record their meals, monitor daily nutritional intake, and track progress toward personalized calorie and protein targets through Telegram.

The system uses natural-language processing to interpret food messages, estimate nutritional values, and maintain daily nutrition summaries.

## Key Features

* **AI-Powered Food Logging:** Understands natural-language food descriptions and identifies individual food items, quantities, and cooking methods.
* **Nutrition Tracking:** Estimates calories, protein, carbohydrates, fats, and fibre for logged meals.
* **Personalized Targets:** Allows users to configure and update daily calorie and protein targets.
* **Daily Nutrition Summary:** Calculates daily nutritional totals and compares them with configured targets.
* **Food Log Management:** Allows users to view recent food entries and delete incorrect entries.
* **Telegram Integration:** Provides an accessible conversational interface for food logging and nutrition queries.
* **Cloud Deployment:** Hosted on an Azure virtual machine using Docker and Cloudflare Tunnel.

## Technologies Used

* **Workflow Automation:** n8n
* **AI Model:** Google Gemini
* **Chat Interface:** Telegram Bot API
* **Data Storage:** Google Sheets
* **Containerization:** Docker
* **Cloud Hosting:** Microsoft Azure
* **Secure Connectivity:** Cloudflare Tunnel

## How It Works

1. The user sends a food description through Telegram.
2. n8n receives the message and sends it to Google Gemini for interpretation.
3. The AI identifies food items, quantities, cooking methods, and estimated nutritional values.
4. The workflow records the food entries in Google Sheets.
5. The system retrieves the user's daily food records and calculates total nutritional intake.
6. Daily summaries are updated and compared with the user's calorie and protein targets.
7. The bot sends the user a response containing the logged meal and nutrition progress.

## Available Commands

| Command            | Purpose                                     |
| ------------------ | ------------------------------------------- |
| `/setup`           | Configure daily calorie and protein targets |
| `/targets`         | View current nutrition targets              |
| `/logs`            | View recent food entries                    |
| `/delete <Log ID>` | Delete a specific food entry                |

## Architecture

**Telegram → n8n → Google Gemini → Google Sheets → Nutrition Calculations → Telegram Response**

The application runs in a Docker container on an Azure virtual machine. Cloudflare Tunnel provides secure HTTPS access to the n8n interface and webhook endpoints.

## Workflow

The exported n8n workflow is available in the `workflow` directory.

Before importing the workflow, configure your own Telegram bot, Google Gemini API access, and Google Sheets credentials in n8n.

## Security

API keys, bot tokens, OAuth credentials, passwords, and private user data must not be committed to the repository.

## Future Improvements

* Migrate nutrition data from Google Sheets to PostgreSQL.
* Improve nutritional estimates using verified food composition data.
* Add weekly and monthly nutrition analytics.
* Improve input validation and error handling.

## Disclaimer

Nutritional values are estimates and may vary depending on ingredients, portion sizes, and preparation methods. The chatbot is intended for general nutrition tracking and is not a substitute for professional medical or dietary advice.

