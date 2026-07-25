# Weather Intelligence App

A weather intelligence web app built with React + Vite. It uses public Open-Meteo APIs for city geocoding, current weather, and 7-day forecast.

## Assignment Coverage

This project includes:
- Live city search using Open-Meteo geocoding API
- Current weather and 7-day forecast from Open-Meteo forecast API
- Invalid city handling with clear error state
- Browser-accessible deployment support for Cloudflare Pages
- Build configuration and deployment notes for evidence submission

## Tech Stack

- React 18
- Vite 8
- TailwindCSS 3
- Express (local dev API integration)
- Cloudflare Pages Functions (`functions/api/weather.js`)

## Local Run

Prerequisites:
- Node.js 22+
- pnpm

Commands:

```bash
npm install
npm run dev
```

Alternative with pnpm:

```bash
pnpm install
pnpm dev
```

Local URL:
- http://localhost:8080

## Deployment (Cloudflare Pages)

Use the connected GitHub repository in Cloudflare Pages and configure:

- Framework preset: None
- Build command: `npm run build`
- Build output directory: `dist`
- Root directory: `/` (repository root)

Cloudflare Pages Functions are in:
- `functions/api/weather.js`

The frontend calls:
- `/api/weather?city=<city-name>`

## API Sources

- Geocoding API: https://geocoding-api.open-meteo.com/v1/search
- Forecast API: https://api.open-meteo.com/v1/forecast

## Validation Checklist (Evidence)

Capture screenshots or short screen recording for:

1. App opened from Cloudflare Pages URL (`*.pages.dev`)
2. Successful search with City 1 (example: London)
3. Successful search with City 2 (example: Tokyo)
4. Invalid city search (example: `abcxyzinvalid`) showing error state
5. Current weather details visible (temperature, condition, wind, humidity)
6. 7-day forecast visible (day, max temp, min temp, weather)
7. Recommendation cards visible (planning recommendation)
8. Cloudflare Pages settings page showing connected GitHub repo, build command, and output directory
9. Deployment success log in Cloudflare
10. Repository page showing source code, config, and README

## Notes

- This app uses only public weather data from Open-Meteo.
- No private keys are required.
- If API responses fail due to network issues, the UI shows an error and allows retry.
