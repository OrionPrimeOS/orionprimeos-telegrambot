# OrionPrimeOS Telegram Bot

A simple Telegram bot powered by Flask and deployed on Render.

## 🚀 Deploy Instructions
1. Push this repo to GitHub.
2. Create a new Render Web Service:
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python -m gunicorn Orionprimeos-telegrambot.main:app --bind 0.0.0.0:$PORT`
3. Add environment variables in Render:
   - `TELEGRAM_TOKEN` = your BotFather token
   - `WEBHOOK_SECRET` = orionprimeos
4. Deploy service.

## 🔌 Connect Telegram
Run these commands from PowerShell (replace token if needed):

```powershell
# Delete old webhook
curl.exe -X POST "https://api.telegram.org/bot<YOUR_TOKEN>/deleteWebhook"

# Set new webhook to /orionprimeos
curl.exe -X POST "https://api.telegram.org/bot<YOUR_TOKEN>/setWebhook?url=https://<YOUR-RENDER-APP>.onrender.com/orionprimeos"

# Verify webhook status
curl.exe -X GET "https://api.telegram.org/bot<YOUR_TOKEN>/getWebhookInfo"
```

## 🧪 Test
1. Open your bot in Telegram.
2. Send `hello`.
3. Bot replies: `You said: hello`.
