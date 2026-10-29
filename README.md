# Kerala 2050 - AI Heritage & Smart Future City

A website with a Claude-powered citizen assistant.

## Run it
1. Install Node.js 20.6 or newer.
2. In this folder run: `npm install`
3. Copy `.env.example` to `.env` and put your Anthropic API key in it
   (create one at https://console.anthropic.com).
4. Run: `npm start` and open http://localhost:3000

## How the chatbot works
Browser -> `POST /api/chat` (your server) -> Claude API -> reply back to the page.
The key lives only in `.env` on the server. If the server or key is missing,
the page falls back to simple built-in answers so the demo never breaks.

## Alternatives to Claude
Edit the `client.messages.create` call in `server.js` to use another provider
(OpenAI, Gemini, or a free local model via Ollama). The frontend does not change.

## Deploying
Host on Render, Railway or any Node host and set `ANTHROPIC_API_KEY` as an
environment variable there. Do not open `index.html` directly from a file if you
want the live AI - it needs the server.

## Features
- Live Claude chatbot with conversation memory, typing indicator, suggestion chips
- Interactive 14-district explorer
- Tabbed heritage museum, animated counters, scroll progress bar
- Dark/light theme saved between visits, mobile menu, accessible markup
- Safe chat rendering (no HTML injection)
