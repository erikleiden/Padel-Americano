# 🎾 Padel Americano Manager

A modern web app for running **Padel Americano** tournaments — the social format where players rotate partners each round so everyone plays with and against different people.

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript)
![Vite](https://img.shields.io/badge/Vite-6-646CFF?logo=vite)
![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-000?logo=vercel)

## Features

### Core Tournament
- ✅ **Smart Scheduling** — Mathematically optimal "Whist" schedules for 8, 12, and 16 players
- ✅ **Court Rotation** — Algorithm ensures players rotate across different courts each round
- ✅ **Custom Court Names** — Label courts (e.g., "Center Court", "Court A") for easy callouts
- ✅ **Live Scoring** — Enter scores per round, see leaderboard update in real-time
- ✅ **Winner Highlighting** — Completed matches show winning team in green

### Flexible Tournament Management
- ✅ **Add Rounds On-Demand** — "+" button to extend tournament with fair player rotation
- ✅ **Championship Round** — Create finals: 1st+3rd vs 2nd+4th place
- ✅ **Championship Results** — Shows winning team, runner-up, and individual rankings
- ✅ **Locked Setup** — Players locked once tournament starts (prevents accidents)

### User Experience
- ✅ **Mobile-First** — Responsive design works great on phones at the courts
- ✅ **Keyboard Navigation** — Arrow keys to navigate between rounds
- ✅ **Offline Ready** — All data persists in localStorage, no account needed
- ✅ **Tie-Breaking** — Sorted by total points → match wins → point differential

## Quick Start

**Prerequisites:** Node.js 18+

```bash
# Install dependencies
npm install

# Start dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## How It Works

### Tournament Flow

1. **Setup** — Add players (4+ required, 8/12/16 for "perfect" balance)
2. **Configure Courts** — Rename courts for your venue (Tab between inputs)
3. **Generate** — Creates all rounds with optimal pairings
4. **Play** — Navigate through rounds, enter scores after each match
5. **Extend** — Add more rounds with "+" button if time permits
6. **Finals** — Create championship round from leaderboard
7. **Results** — See team champions and individual rankings

### Scheduling Algorithm

The app uses **Whist Tournament** logic:

| Players | Rounds | Courts | Balance |
|---------|--------|--------|---------|
| 8 | 7 | 2 | Partner everyone once, oppose everyone twice |
| 12 | 11 | 3 | Partner everyone once, oppose everyone twice |
| 16 | 15 | 4 | Partner everyone once, oppose everyone twice |
| Other | N-1 | Varies | Berger table rotation (partner everyone once) |

**Court Rotation**: Players automatically rotate between courts each round — the algorithm tracks court history and optimizes assignments.

**Additional Rounds**: When adding rounds on-demand, the algorithm:
- Prioritizes players who've played fewer matches
- Avoids recent partner/opponent pairings
- Handles byes for odd player counts

## Development

```bash
npm run dev      # Development server with HMR
npm run build    # Production build
npm run preview  # Preview production build locally
```

## Project Structure

```
├── App.tsx              # Main React component (UI + state)
├── types.ts             # TypeScript interfaces
├── utils/
│   └── scheduler.ts     # Tournament scheduling + additional rounds
├── index.tsx            # React entry point
├── index.html           # HTML shell + Tailwind CDN
└── CLAUDE.md            # AI agent context file
```

## Deployment

The app is deployed on **Vercel**. Push to `main` for production, or create a PR for a preview deployment.

## Contributing

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Make changes and test locally
3. Open a PR — Vercel will generate a preview link
4. Merge after review

## License

MIT

---

<details>
<summary>Original AI Studio Info</summary>

This project was bootstrapped with Google AI Studio.

View in AI Studio: https://ai.studio/apps/drive/1oXCLn8u0242Op7GnKGWZ8KPmGR3-3US1

</details>
