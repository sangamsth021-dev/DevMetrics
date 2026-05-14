[README (3).md](https://github.com/user-attachments/files/27751892/README.3.md)
<div align="center">

<h1>
  <br>
  <img src="https://img.shields.io/badge/Dev-Metrics-00E5A5?style=flat-square&labelColor=07090F&color=00E5A5" alt="DevMetrics" height="36">
  <br>
  DevMetrics — GitHub Analytics Dashboard
  <br>
</h1>

<p>
  <strong>Visualize any GitHub profile with contribution heatmaps, language breakdowns,<br>repository insights, and deep activity analytics — all in a single file, zero backend.</strong>
</p>

<!-- BADGES -->
<p>
  <img src="https://img.shields.io/badge/built_with-D3.js_+_Chart.js-00E5A5?style=flat-square&labelColor=0C0F1C" alt="Built with D3.js + Chart.js">
  <img src="https://img.shields.io/badge/runtime-zero_dependencies-7C5CFA?style=flat-square&labelColor=0C0F1C" alt="Zero runtime dependencies">
  <img src="https://img.shields.io/badge/data-GitHub_REST_API-F5A623?style=flat-square&labelColor=0C0F1C" alt="GitHub REST API">
  <img src="https://img.shields.io/badge/deploy-single_HTML_file-FF5F7E?style=flat-square&labelColor=0C0F1C" alt="Single HTML file">
  <img src="https://img.shields.io/badge/license-MIT-4DA8FF?style=flat-square&labelColor=0C0F1C" alt="MIT License">
</p>

<!-- LIVE DEMO -->
<br>

### 🚀 [**Live Demo →**](https://dev-metrics-murex.vercel.app/)
> _Replace the link above with your deployed URL (GitHub Pages, Vercel, Netlify, etc.)_

<br>

---

</div>

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Option 1 — Open Locally](#option-1--open-locally)
  - [Option 2 — Deploy to GitHub Pages](#option-2--deploy-to-github-pages)
  - [Option 3 — Deploy to Vercel / Netlify](#option-3--deploy-to-vercel--netlify)
- [GitHub API Token](#github-api-token)
- [Architecture](#architecture)
- [Dashboard Sections](#dashboard-sections)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [URL Parameters](#url-parameters)
- [Export Format](#export-format)
- [API Rate Limits](#api-rate-limits)
- [Browser Support](#browser-support)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

**DevMetrics** is a fully client-side GitHub profile analytics dashboard. It fetches data directly from the [GitHub REST API](https://docs.github.com/en/rest), processes it in the browser, and renders interactive visualizations — no server, no database, no build step.

Open `devmetrics.html` in any modern browser and type a GitHub username. That's it.

```
devmetrics.html   ← the entire application lives here (~67 KB)
README.md
```

---

## Features

### 📊 Overview Tab
| Feature | Description |
|---|---|
| **Profile Card** | Avatar, bio, location, company, website, Twitter, direct GitHub link |
| **4 Stat Counters** | Public repos, total stars, followers, recent events — all with count-up animation |
| **Streak Cards** | Current streak, longest streak, account age |
| **Contribution Heatmap** | 53-week D3.js heatmap built from public event data, with per-cell tooltips |
| **30-Day Activity Chart** | Day-by-day public event bar chart (Chart.js) |
| **Language Donut** | Proportional language breakdown with bar chart legend |
| **Top Repositories** | Top 6 repos by stars, with description, topics, stats, and last-updated time |
| **Star Distribution** | Horizontal bar chart across top 8 repos |
| **Highlights Panel** | Most starred, most forked, average stars per repo, total open issues, primary language |

### 📁 Repositories Tab
| Feature | Description |
|---|---|
| **Live Search** | Filter repos by name or description instantly as you type |
| **Language Filter** | Dropdown auto-populated from the user's actual repo languages |
| **Sort Options** | Stars ↓, Forks ↓, Recently Updated, Name A→Z, Open Issues ↓, Repo Size ↓ |
| **Fork Toggle** | Show or hide forked repositories |
| **Card / List View** | Switch between a grid of cards and a compact list view |
| **GitHub Topics** | Topics displayed as inline tags on each repository card |
| **Pagination** | Shows first 18 repos; "Show more" loads additional batches without a page reload |

### ⚡ Activity Tab
| Feature | Description |
|---|---|
| **Event Breakdown** | Horizontal bar chart of all event types (Push, PR, Fork, Star, Release, etc.) |
| **Day-of-Week Chart** | Bar chart showing which day of the week the user is most active |
| **Hourly Distribution** | 24-hour bar chart highlighting peak coding hours (UTC) |
| **Hour × Day Heatmap** | D3.js 7×24 grid — the most granular view of when someone codes |
| **Full Event Feed** | Scrollable list of all 300 fetched public events with commit messages |

### 🛠 Utility Features
| Feature | Description |
|---|---|
| **GitHub Token Input** | Optional PAT input; auto-validates against `/rate_limit` and glows green when accepted |
| **Rate Limit Badge** | Live indicator in the header showing remaining/total API calls, color-coded |
| **Share Button** | Copies a `?user=username` URL to the clipboard for direct sharing |
| **JSON Export** | Downloads a structured `.json` file with full profile, repo, and analytics data |
| **URL Parameters** | `?user=torvalds` auto-triggers analysis on page load |
| **Keyboard Shortcuts** | `/` to focus search, `Alt+1/2/3` to switch tabs |
| **Responsive Layout** | Fully adaptive from 375px mobile to 1440px+ desktop |
| **Print Stylesheet** | Clean layout when printing or saving as PDF |

---

## Screenshots

> _Add screenshots here after deployment._

```
screenshots/
├── overview.png       ← Profile + heatmap + charts
├── repositories.png   ← Filtered repo grid
└── activity.png       ← Event breakdown + hour×day heatmap
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Visualizations** | [D3.js v7](https://d3js.org) — contribution heatmap, hour×day grid |
| **Charts** | [Chart.js v4](https://www.chartjs.org) — bar charts, donut chart |
| **Fonts** | [Space Mono](https://fonts.google.com/specimen/Space+Mono), [DM Sans](https://fonts.google.com/specimen/DM+Sans), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) via Google Fonts |
| **Data** | [GitHub REST API v3](https://docs.github.com/en/rest) — unauthenticated or token-authenticated |
| **Runtime** | Vanilla JavaScript (ES2020+), no frameworks, no bundler |
| **Deployment** | Any static file host — GitHub Pages, Vercel, Netlify, Cloudflare Pages |

No `npm install`. No `package.json`. No build pipeline.

---

## Getting Started

### Option 1 — Open Locally

```bash
# Clone the repo
git clone https://github.com/your-username/devmetrics.git
cd devmetrics

# Open directly in your browser
open devmetrics.html          # macOS
start devmetrics.html         # Windows
xdg-open devmetrics.html      # Linux
```

Or just **double-click** `devmetrics.html`. No local server needed.

---

### Option 2 — Deploy to GitHub Pages

```bash
# 1. Fork or clone this repo
git clone https://github.com/your-username/devmetrics.git
cd devmetrics

# 2. Push to GitHub
git remote set-url origin https://github.com/YOUR_USERNAME/devmetrics.git
git push -u origin main

# 3. Go to your repo on GitHub
#    Settings → Pages → Source: Deploy from branch → Branch: main / (root)
#    Your site will be live at: https://YOUR_USERNAME.github.io/devmetrics/
```

> Update the **Live Demo** link at the top of this README once it's deployed.

---

### Option 3 — Deploy to Vercel / Netlify

**Vercel:**
```bash
npm i -g vercel
vercel --yes
```

**Netlify (drag & drop):**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop `devmetrics.html`
3. Done — instant public URL

**Netlify CLI:**
```bash
npm i -g netlify-cli
netlify deploy --prod --dir .
```

---

## GitHub API Token

By default, the GitHub REST API allows **60 unauthenticated requests per hour** per IP address. Each profile analysis uses approximately 5–8 API calls, so you can analyze roughly 7–12 profiles per hour without a token.

To increase this to **5,000 requests per hour**, add a Personal Access Token:

1. Go to [GitHub → Settings → Tokens (classic)](https://github.com/settings/tokens/new?scopes=read:user&description=DevMetrics)
2. Select scope: **`read:user`** (read-only, no write access needed)
3. Generate and copy the token
4. Paste it into the **"Token (optional)"** field in the DevMetrics header

The token is never sent anywhere except the GitHub API. It lives only in the input field for the duration of your session.

> **Security note:** DevMetrics has no backend. Your token is never logged, stored, or transmitted to any third-party server.

---

## Architecture

```
devmetrics.html
│
├── <style>          CSS custom properties + all component styles
│
├── <header>         Search input, Analyze button, token input,
│                    rate-limit badge, Share/Export buttons
│
├── <nav.tabs>       Overview | Repositories | Activity (sticky)
│
├── <main>           Dynamic content area — one of:
│   ├── Landing      Hero + feature chips + example profile buttons
│   ├── Loading      Animated spinner + step-by-step progress list
│   ├── Error        Friendly error message + retry button
│   └── Dashboard    Three tab panels (rendered on demand)
│       ├── #ov-panel   Overview (profile, heatmap, charts, repos)
│       ├── #rp-panel   Repositories (filter bar + grid/list)
│       └── #ac-panel   Activity (event analytics + event feed)
│
└── <script>
    ├── CONSTANTS    Language colors, event palette
    ├── STATE        S{} — user, repos, events, tab, filter state
    ├── API          gh(), fetchRepos(), fetchEvents()
    ├── DATA         langs(), heat(), streak(), dow(), hourly(), hdgrid()
    ├── CHARTS       mkChart(), initOV(), initAC()
    ├── D3           drawHeat(), drawHD()
    ├── BUILDERS     buildOV(), buildRP(), buildAC()
    ├── FILTERS      applyF(), setRF(), togRF(), loadMore()
    ├── UI           gotoTab(), animCnt(), toast(), updateRL()
    └── ENTRY        analyze(), go(), doShare(), doExport()
```

Tab panels are built once and cached. Charts are initialized lazily — only when their tab is first visited — and destroyed/recreated if the user runs a new analysis.

---

## Dashboard Sections

### Contribution Heatmap

Built with D3.js. Covers the **last 53 weeks** (same as GitHub's calendar). Each cell represents one day; color intensity is based on the number of public events recorded that day.

> **Limitation:** GitHub's full contribution count (including private repos) requires the GraphQL API with an authenticated token. DevMetrics uses the REST Events API, which only covers public activity and is capped at the 300 most recent events (~90 days of typical activity). Add a token for the best results.

### Hour × Day Heatmap

A 7 × 24 grid (days of week × hours of day) built with D3.js. All times are in **UTC**. Hover any cell to see the exact day/hour and event count. This is the most precise view of *when* a developer is active.

### JSON Export

The exported file has the following structure:

```json
{
  "meta": {
    "exportedAt": "2025-01-15T10:30:00.000Z",
    "source": "DevMetrics",
    "github": "https://github.com/username"
  },
  "profile": { ...GitHub user object... },
  "stats": {
    "totalStars": 12400,
    "totalForks": 3200,
    "totalRepos": 87,
    "totalEvents": 300,
    "languages": [{ "lang": "JavaScript", "cnt": 34, "pct": 39 }, ...],
    "eventTypes": [["Push", 187], ["Create", 42], ...]
  },
  "repos": [
    {
      "name": "my-repo",
      "description": "...",
      "language": "TypeScript",
      "stars": 4200,
      "forks": 890,
      "openIssues": 23,
      "topics": ["react", "typescript"],
      "url": "https://github.com/...",
      "updatedAt": "2025-01-10T08:00:00Z",
      "size": 14820,
      "fork": false,
      "archived": false
    }
  ]
}
```

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `/` | Focus the username search input |
| `Ctrl + K` | Focus the username search input |
| `Enter` | Run analysis (when search input is focused) |
| `Alt + 1` | Switch to **Overview** tab |
| `Alt + 2` | Switch to **Repositories** tab |
| `Alt + 3` | Switch to **Activity** tab |

---

## URL Parameters

DevMetrics supports deep-linking via URL query parameters.

| Parameter | Example | Effect |
|---|---|---|
| `user` | `?user=torvalds` | Auto-loads and analyzes the given username on page open |

**Examples:**
```
https://your-demo.com/?user=torvalds
https://your-demo.com/?user=gaearon
https://your-demo.com/?user=sindresorhus
```

The Share button automatically generates and copies these URLs to your clipboard.

---

## API Rate Limits

| Mode | Requests/hour | Notes |
|---|---|---|
| No token | 60 / hour | Per IP address |
| Personal Access Token | 5,000 / hour | Per token |

**Calls made per analysis:**
- `GET /users/{username}` — 1 call
- `GET /users/{username}/repos` — 1–3 calls (100 repos/page, up to 300 repos)
- `GET /users/{username}/events/public` — 1–3 calls (100 events/page, up to 300 events)

**Total: ~5–7 calls per profile analyzed.**

At 60 req/hr unauthenticated, you can analyze approximately **8–10 profiles per hour**. With a token: **700+ profiles per hour**.

The rate-limit badge in the header updates automatically after every API call and turns **yellow** below 100 remaining, **red** below 10.

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Mobile Chrome | ✅ Full (responsive) |
| Mobile Safari | ✅ Full (responsive) |

Requires: `fetch`, `async/await`, CSS custom properties, ES2020 (`optional chaining`, `nullish coalescing`).

---

## Roadmap

- [ ] **Full contribution graph** via GitHub GraphQL API (requires token)
- [ ] **Compare mode** — side-by-side stats for two GitHub users
- [ ] **Organization support** — analyze org repos and members
- [ ] **Pinned repos** — surface pinned repos via GraphQL API
- [ ] **Commit frequency heatmap** per repository
- [ ] **Follower/following network** visualization (D3 force graph)
- [ ] **Dark/light theme toggle**
- [ ] **Caching** — localStorage cache with configurable TTL to reduce API calls
- [ ] **PWA** — service worker for offline access and installability
- [ ] **Language trend** — track language usage changes over time

---

## Contributing

Contributions are welcome! Since this is a single-file project, the contribution flow is simple:

```bash
# 1. Fork the repository
# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/devmetrics.git

# 3. Make changes to devmetrics.html
# 4. Test by opening in a browser

# 5. Commit and push
git add devmetrics.html
git commit -m "feat: add XYZ feature"
git push origin main

# 6. Open a Pull Request
```

**Guidelines:**
- Keep it a single file — no build step, no bundler, no `node_modules`
- Test against the GitHub API rate limits (unauthenticated + token)
- Maintain the dark industrial visual theme
- Add keyboard accessibility for any new interactive elements
- Update this README for any new features, shortcuts, or URL parameters

---

## License

```
MIT License

Copyright (c) 2025 DevMetrics Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

Built with care using D3.js, Chart.js, and the GitHub REST API.

**[⬆ Back to top](#devmetrics--github-analytics-dashboard)**

</div>
