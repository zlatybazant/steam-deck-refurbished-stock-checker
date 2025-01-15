# Steam Deck Refurbished Stock Checker

## Description

This project provides a script to monitor the availability of refurbished Steam Deck units on the official store page and send a notification to a specified Discord channel when stock is detected. The script uses Selenium for web scraping and a Discord webhook for notifications.

## Prerequisites

Before using this script, ensure the following dependencies are installed:

1. Python 3 
2. Chromium or Google Chrome and ChromeDriver (compatible with your version of Chromium/Google Chrome). E.g for Ubuntu 24.04:
    ```sh
    sudo apt install chromium-browser chromium-chromedriver
    ```
4. Selenium and Requests Python packages (specified in requirements.txt)
    ```sh
    pip install -r requirements.txt
    ```

## Setup Instructions

1. Clone the repository:
    ```sh
    git clone <repository-url>
    cd steam-deck-stock-checker
    ```
2. Set up your Discord Webhook URL:
    - Create 'env.py' and pass below env variable and 'YOUR_DISCORD_WEBHOOK_URL' with your actual Discord webhook URL:
    ```python
    DISCORD_WEBHOOK_URL = 'YOUR_DISCORD_WEBHOOK_URL'
    ```
3. Set permissions and scheduling:
    - Ensure `script.sh` is executable:
    ```sh
    chmod +x script.sh
    ```
    - Add `script.sh` to a cron job to check for stock periodically (every 5 minutes in this example):
    ```sh
    */5 * * * * /path/to/steam-deck-refurbished-stock-checker/script.sh >> /path/to/steam-deck-refurbished-stock-checker/logfile.log 2>&1
    ```

    - Add logfile removal to a cron job every day:
    ```sh
    0 0 * * * rm -f /path/to/steam-deck-refurbished-stock-checker/logfile.log
    ```

## Disclaimer

This script is provided "as is" for personal use. Be aware of website scraping policies and use responsibly.
