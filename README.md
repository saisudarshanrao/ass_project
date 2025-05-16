Telegram .onion Link Extractor project:

# Telegram .onion Link Extractor



##  What It Does

- Connects to a specified Telegram channel (e.g., `@toronionlinks`)
- Parses recent messages for `.onion` (Tor) URLs
- Saves the extracted links in a structured JSON format
- Tracks the last scanned message to avoid duplicates
- Fully compatible with Jupyter Notebooks / Google Colab

---



- Python 3.7+
- `telethon` library
- Telegram API credentials from [my.telegram.org](https://my.telegram.org)
- A valid `.session` file (must be generated locally by logging in once)

Install dependencies:

```bash
pip install telethon


Setup Instructions
1. Get Telegram API Credentials
Go to https://my.telegram.org

Create a new application to get:

API_ID

API_HASH

2. Create a Session File Locally

from telethon import TelegramClient
import asyncio

api_id = YOUR_API_ID
api_hash = 'YOUR_API_HASH'
session_name = 'projectt'

async def main():
    client = TelegramClient(session_name, api_id, api_hash)
    await client.start
    print("Session created.")
    await client.disconnect()

await main()

Output Format
Each discovered link is saved in onion_links.json with the structure:

json
Copy
Edit
{
  "source": "telegram",
  "url": "http://exampleonion123.onion",
  "discovered_at": "2025-05-16T10:00:00Z",
  "context": "Found in Telegram channel @toronionlinks",
  "status": "pending"
}
