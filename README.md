# Eva AI — Fraud Protection for Elderly Banking Customers

Eva is a real-time AI fraud detection assistant built for the bunq hackathon. It monitors payments and blocks scams before money leaves the account — designed specifically to protect elderly Dutch bank customers.

## What it does

- **Real-time payment analysis** — every payment is scored for fraud risk using Claude Sonnet 4.6
- **Auto-blocks high-risk payments** — grandparent scams, fake helpdesks, bank impersonation, lottery fraud, crypto fraud
- **Pauses medium-risk payments** — user must explicitly approve or reject
- **Phishing image scanner** — upload a screenshot of a suspicious message and get an instant verdict
- **Conversational AI chat** — Eva explains every decision in plain, calm language
- **bunq safety notice** — every blocked payment shows official guidance

## Risk levels

| Level | Score | Action |
|-------|-------|--------|
| 🔴 HIGH RISK | 70–100 | Auto-blocked, user notified |
| 🟡 SOFT WARNING | 45–69 | Paused, user must approve or reject |
| 🟢 SAFE | 0–44 | Processed normally |

## Tech stack

- **Runtime**: Node.js + Express
- **AI**: Anthropic API — Claude Sonnet 4.6 (fraud detection, vision, chat)
- **Real-time**: WebSocket (`ws`)
- **Database**: SQLite (`better-sqlite3`)
- **Frontend**: Vanilla HTML/CSS/JS
- **Banking**: bunq API (sandbox)

## Getting started

```bash
npm install
```

Create a `.env` file:

```
ANTHROPIC_API_KEY=your_key_here
BUNQ_API_KEY=your_key_here
BUNQ_SANDBOX=true
PORT=3000
```

Start the server:

```bash
node server/index.js
```

Open `http://localhost:3000`

## Scam types detected

- Grandparent scam (opa/oma fraud)
- Helpdesk fraud (Microsoft, TeamViewer)
- Bank impersonation (veilige rekening, fraudeafdeling)
- Lottery & prize fraud (loterij gewonnen, prize center)
- Crypto fraud (bitcoin withdrawal, investment return)
- Phishing emails & WhatsApp messages

## Built at

bunq Hackathon 2026
