# 🌦️ n8n-workflows

Hey! 👋 This is where my automations live. Every workflow here runs on my own self-hosted [n8n](https://n8n.io) box — no Zapier bills, no "you've hit your task limit," just my own little robots doing chores while I sleep.

Backed up here automatically, every night. Because losing work you built at 2 AM hits different.

---

## 🚀 What's in here

### Daily Weather Email — `workflows/Hgtj2EjQlWPzuTxM.json`

Built this one first. Every morning at **6 AM**, before I'm even awake, this thing:

1. ☁️ Pulls today's forecast for my city
2. 🧠 Turns a boring weather code like `2` into actual words — "Partly cloudy"
3. 📬 Emails me a clean little summary: high, low, and conditions

So I wake up, check my inbox, and already know if I need a jacket. No app, no ads, no doomscrolling a weather site. Just the answer, waiting for me.

**How it works:**

```
⏰ Schedule Trigger  →  🌐 Get forecast (Open-Meteo)  →  🧠 Translate the code  →  📧 Email me
```

**The stack:**
- **n8n** (self-hosted, Community edition) on a Hostinger VPS — one-click deploy, HTTPS out of the box
- **Open-Meteo** for the forecast — free, no API key, no nonsense
- **Gmail** for delivery

---

## 🛠️ Wanna build your own?

The gist:

1. Get n8n running (I used Hostinger's one-click n8n template — 10 minutes, done).
2. Drop a **Schedule Trigger** and set your time + timezone.
3. Add an **HTTP Request** node hitting Open-Meteo with your coordinates.
4. Add a **Code** node to turn the weather number into readable text.
5. Wire up **Gmail** and map the forecast into the email.
6. Connect them, hit activate, go touch grass. ☘️

---

## 🔒 A note on safety

These are full workflow exports, but **no secrets live in here** — n8n keeps API keys and tokens encrypted and separate, so what you see is just the wiring, never the passwords.

---

*Everything here is backed up automatically by another n8n workflow that pushes to this repo nightly. Set it up once, never think about it again. That's the whole point. 😎*
