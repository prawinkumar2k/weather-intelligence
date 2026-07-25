# Weather Intelligence App

[![Build](https://img.shields.io/badge/build-passing-brightgreen)](#local-development)
[![Frontend](https://img.shields.io/badge/frontend-React%20%2B%20Vite-61dafb)](#tech-stack)
[![Deploy](https://img.shields.io/badge/deploy-Cloudflare%20Pages-orange)](#cloudflare-pages-deployment)
[![API](https://img.shields.io/badge/api-Open--Meteo-blue)](#api-integration)

Weather Intelligence is a responsive weather web application that helps users search any city and instantly view current conditions, a 7-day forecast, and planning recommendations.

This project is built to satisfy the Level 2 app-building lifecycle: design, implementation, API integration, testing, deployment, and evidence-based submission.

## Live Assignment Coverage

### Functional Requirements

- City search
- Current weather: temperature, condition, wind, humidity
- 7-day forecast: day, max/min temperature, weather condition
- Weather recommendations
- Invalid city and API error handling

### Validation Scenarios

- Valid city test: Chennai
- Valid city test: Bangalore
- Invalid city test: InvalidCity987654

## Architecture

```mermaid
flowchart LR
	U[User] --> FE[React Frontend]
	FE --> API[/api/weather]
	API --> GEO[Open-Meteo Geocoding API]
	API --> FC[Open-Meteo Forecast API]
	FC --> API
	API --> FE
```

### Runtime Paths

- Local development: Vite + Express route handling
- Cloud deployment: Cloudflare Pages + Pages Functions

## Tech Stack

- React 18
- Vite 8
- JavaScript (JSX)
- Tailwind CSS 3
- Express 5 (local API orchestration)
- Cloudflare Pages Functions
- Open-Meteo APIs

## Project Structure

```text
weather-intelligence/
├─ client/
│  ├─ components/
│  ├─ hooks/
│  ├─ lib/
│  ├─ pages/
│  ├─ App.jsx
│  └─ global.css
├─ functions/
│  └─ api/
│     └─ weather.js
├─ server/
│  ├─ routes/
│  │  ├─ demo.js
│  │  └─ weather.js
│  ├─ index.js
│  └─ node-build.js
├─ public/
├─ package.json
├─ vite.config.js
├─ SUBMISSION_CHECKLIST.md
└─ VIVA_SCRIPT.md
```

## Local Development

### Prerequisites

- Node.js 20+ (22 recommended)
- npm or pnpm

### Run

```bash
npm install
npm run dev
```

App URL:

- http://localhost:8080

### Build

```bash
npm run build
```

Build output:

- dist

## API Integration

### Open-Meteo Geocoding

- Endpoint: https://geocoding-api.open-meteo.com/v1/search
- Purpose: Convert city name to latitude/longitude

### Open-Meteo Forecast

- Endpoint: https://api.open-meteo.com/v1/forecast
- Purpose: Current weather + 7-day forecast data

### Frontend API Call

- Route: /api/weather?city=<city-name>

## Cloudflare Pages Deployment

Use these exact settings:

| Setting | Value |
|---|---|
| Framework Preset | Vite |
| Build Command | npm run build |
| Build Output Directory | dist |
| Root Directory | / |
| Node Version | 20 |
| Environment Variables | None |

## Quick QA Checklist

- Search Chennai and verify weather sections render
- Search Bangalore and verify weather sections render
- Search InvalidCity987654 and verify friendly error
- Confirm no obvious browser console runtime errors
- Check responsive behavior on desktop and mobile viewport

## Evidence Checklist (For Submission)

Capture screenshots of:

1. GitHub repository home page
2. README on GitHub
3. Cloudflare build configuration
4. Cloudflare successful deployment screen
5. Live pages.dev URL/home page
6. Chennai search result
7. Bangalore search result
8. Invalid city result

## Security and Data Notes

- Uses only public Open-Meteo APIs
- No private API keys required
- No Firebase, no Gemini API, no Google Cloud APIs
- Invalid input and failed API calls are handled with user-friendly errors

## Documentation Helpers

- Submission checklist: SUBMISSION_CHECKLIST.md
- Viva/demo script: VIVA_SCRIPT.md

## License

This project currently has no explicit license file.
For open-source usage, add an MIT License file.
