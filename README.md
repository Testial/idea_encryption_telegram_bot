
# IDEA Encryption Telegram Bot

This repository contains a small Telegram bot that implements the IDEA (International Data Encryption Algorithm) block cipher. The bot supports several modes of operation (ECB, CBC, CFB, OFB, CTR) and multiple padding schemes for the final block (ANSI X.923, ISO 10126, PKCS7, ISO/IEC 7816-4).

The project is written in Python and uses aiogram for Telegram interaction.

## Key points
 - By default the bot returns encrypted output as base64 text in the chat (easy to copy/paste).
 - You can switch the output to a binary file using the `/format` command (choose `binary file`).
 - Decryption accepts either a binary file (document) or a base64 text message.

## Links
 - Bot (if running publicly): [@idea_encrypt_bot](https://t.me/idea_encrypt_bot)
 - Developers: https://t.me/vladkhmarenko, https://t.me/testial95

## Tech stack
 - Python
 - aiogram

## Requirements
Install project dependencies with pip (see `requirements.txt`):

```powershell
python -m pip install -r requirements.txt
```

## Quick setup and usage

1. Create a Telegram bot using [@BotFather](https://t.me/BotFather) and get your BOT_TOKEN.
2. Create a `.env` file in the project root and place the token there following the `.env.example` scheme. Example line:

    ```ini
    BOT_TOKEN=123456789:ABCdefGHIjklMNOpqRSTuvWXyz
    ```

3. Create and activate a virtual environment (optional):

    Windows (PowerShell):

    ```powershell
    python -m venv .venv
    .venv\Scripts\Activate.ps1
    ```

    Linux / macOS:

    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

4. Install dependencies:

    ```powershell
    python -m pip install -r requirements.txt
    ```

5. Run the bot:

    ```powershell
    python main.py
    ```

## How to use the bot (in chat)

 - `/start` — start interaction. The bot initializes user preferences and by default sets the output format to `base64`.
 - `/help` — show usage instructions.
 - `/mode` — choose encryption mode (ECB, CBC, CFB, OFB, CTR).
 - `/padding` — choose block padding (ANSI X.923, ISO 10126, PKCS7, ISO/IEC 7816-4).
 - `/format` — choose output format: `base64` (default) or `binary file`.
 - `/encrypt` — bot will ask for a password (the key), then ask for the text to encrypt. If the format is `base64` the bot will reply with a base64 string. If the format is `binary file` it will send a `.bin` file.
 - `/decrypt` — bot will ask for a password (the key), then accept either a document (binary file) or a base64 text message. The bot will return the decrypted plaintext.

## Notes
 - Default behavior is base64 textual output so you can copy and paste encrypted payloads easily. If you need a binary file, switch to `/format -> binary file` before encrypting.
 - The bot requires you to select `/mode` and `/padding` before encryption/decryption. The `/format` setting is optional since it defaults to `base64`.
