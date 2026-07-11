# cubeport-data
## URL: https://cubeport.vercel.app
<img width="800" height="496" alt="fullweb-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/32da2435-67c7-4d00-b685-bfe452fa0013" />

### Threat Map Demo:
<img width="800" height="496" alt="threatmap-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/2fede29f-6e06-4e45-a206-ba2869ab1d0d" />

---

#### Globe:
- Auto-rotating heatmap globe, drag to spin
- Realistic 3D terrain globe mode
- Victim/Attacker heat map (country density shading)
- Threats ↔ ransomware victims view toggle
- Toggleable pings: C2, malware hosts, abusive IPs, campaign IoCs
- Hover any dot: malware family, status, threat actor
- Click a ping: detail card with copyable IPs, source, first seen

---

#### Data:
- Live feeds, refreshed every 15 minutes
- Stats strip: tracked IPs, countries, top source, data age
- Attacker/Victim country leaderboard
- Live incident news feed: ransomware claims, exploited CVEs, headlines
- Scroll shrinks the globe to reveal the feed
- "?" methodology notes on every legend item

---

### Full Web Demo:
#### Terminal:
- Fake Linux filesystem: ls, cd, pwd, cat, mkdir, touch
- Hidden privesc CTF: follow the breadcrumbs, root the box, cat the flag
- rm -rf / nukes the page (--no-preserve-root respected), make -rf / restores
- rm/make any page element (title, cube, posts, ...)
- Tab completion, ↑/↓ history, "?" command reference
- asciiquarium, cmatrix, neofetch, cowsay

---

#### ASCII Toys:
- Spinning cube / triangle / donut: speed, direction, size, ANSI colors
- Flag capture: rainbow confetti, shape turns rainbow and becomes a draggable bouncy toy
- Procedural bonsai, new tree every page load
- X-ray hover: inverts glyphs under the cursor
- Cursor spotlight reveal with size slider (hidden smiley somewhere)
- Scroll-shifting background gradient

---

#### Pages:
- Hash-routed: home, posts, map, terminal-styled 404
- Posts: reading time, per-post share cards, Thai + English
- One post ships obfuscated until you press deobfuscate
- Accordion panels: education, projects, certifications, work, extra
- Live GitHub contribution calendar
- CV download + socials
- Cookieless analytics
- Respects reduced motion

---
***
---

# cubeport — Everything Under the Hood

Every technology, feed and borrowed idea behind the site, in one list. Live data lands in [cubeport-data](https://github.com/yoscha1/cubeport-data), the public mirror the map reads from.

## Features

- Toggleable threat pings
- Victim/attacker heat map
- Realistic 3D globe mode
- Live incident news feed
- Attacker/victim country leaderboard
- Fake-Linux terminal with a privesc CTF
- Spinning ASCII cube, triangle and donut
- Procedural ASCII bonsai, new tree every load
- Cursor spotlight reveal and x-ray hover
- asciiquarium and cmatrix takeovers
- Hash-routed posts with static share cards
- Cookieless analytics

## Core

- [React 19](https://react.dev) — UI
- [TypeScript](https://www.typescriptlang.org) — types everywhere
- [Vite](https://vite.dev) — dev server and build
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/) + [Chakra Petch](https://fonts.google.com/specimen/Chakra+Petch) — self-hosted via [Fontsource](https://fontsource.org)

## Globe and graphics

- [amCharts 5](https://www.amcharts.com) — heatmap globe, built from the [rotating globe demo](https://www.amcharts.com/demos/rotating-globe/)
- [CesiumJS](https://cesium.com/platform/cesiumjs/) — realistic 3D earth, terrain from the [Cesium ion](https://ion.cesium.com) free tier, lazy-loaded (~1 MB gzipped)
- [PyBonsai](https://github.com/Ben-Edwards44/PyBonsai) — the ASCII bonsai is a port of it
- [Donut.c](https://github.com/sleepymalc/Donut.c) — ASCII donut, the classic [donut math](https://www.a1k0n.net/2011/07/20/donut-math.html)
- Everything else is hand-rolled Canvas 2D: spotlight, matrix rain, aquarium, confetti

## Threat intel feeds

- [Feodo Tracker](https://feodotracker.abuse.ch) — live botnet C2 IPs, by [abuse.ch](https://abuse.ch)
- [ThreatFox](https://threatfox.abuse.ch) — recent IOCs across malware families (abuse.ch)
- [URLhaus](https://urlhaus.abuse.ch) — hosts actively serving malware (abuse.ch)
- [AlienVault OTX](https://otx.alienvault.com) — campaign pulses with threat actor attribution
- [AbuseIPDB](https://www.abuseipdb.com) — most-reported abusive IPs
- [C2IntelFeeds](https://github.com/drb-ra/C2IntelFeeds) — community-tracked C2 infrastructure

## Incident feed

- [ransomware.live](https://www.ransomware.live) — fresh ransomware victim claims
- [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) — CVEs confirmed exploited in the wild
- [The Record](https://therecord.media) + [The Hacker News](https://thehackernews.com) — headlines via RSS

## Pipeline and hosting

- [Vercel](https://vercel.com) — static hosting plus one serverless function (`api/send.js`)
- [GitHub Actions](https://github.com/features/actions) — ingest cron every 15 minutes (`.github/workflows/threat-ingest.yml`), plus CI
- [cron-job.org](https://cron-job.org) — external trigger, because Actions cron drifts and pauses on quiet repos
- [ip-api.com](https://ip-api.com) — batch IP geolocation, cached in the repo (`scripts/geo-cache.json`)
- [cubeport-data](https://github.com/yoscha1/cubeport-data) — public data mirror; `events.json` + `news.json` are the whole backend

## Analytics

- [Umami](https://umami.is) — cookieless pageviews, proxied through `/stats` so adblockers do not eat it

## Quality

- [Playwright](https://playwright.dev) — smoke tests
- [oxlint](https://oxc.rs) — linting
- CI runs lint, type-check, build and tests on every push

All free tiers. $0 a month.


