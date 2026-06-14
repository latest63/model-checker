# Model Access Checker

A simple tool to check which models your API key can actually use — by testing each one with a real request, not just listing them.

## Usage

Open `index.html` in a browser. If your API blocks CORS from file://, serve it:

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080.

## Vercel Deploy (one click)

[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/latest63/model-checker)

Or import from GitHub directly:
1. Go to [vercel.com/new](https://vercel.com/new)
2. Import the `latest63/model-checker` repo
3. Vercel auto-detects static config — just hit **Deploy**

## How it works

1. Enter Base URL + API Key
2. Fetches `/v1/models` for the full list
3. Tests **every chat-capable model** with a `max_tokens=1` request
4. Shows Usable vs Blocked vs Skipped
