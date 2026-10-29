# Project Touchline

A mobile-first football management simulation focused on squad building, tactical decisions, club development, and a fictional Ghanaian league.

> **Current status:** playable browser prototype. It is not yet a complete Football Manager competitor or a signed Android release.

## Features in this foundation

- Responsive dark sports-management interface for mobile and desktop.
- Eight fictional clubs in a home-and-away league (14 matchdays).
- League table with points, goal difference, and recent form.
- Simulated match results, goal events, match timeline, shots, and possession.
- Matchday injury events, temporary player unavailability, squad availability labels, and medical-facility recovery upgrades.
- Player discipline: yellow-card accumulation, red-card incidents, matchday suspensions, and automatic exclusion of suspended players from the starting XI.
- Tactical board and four formations: 4-3-3, 4-2-3-1, 4-4-2, and 3-5-2.
- Team mentality, pressing intensity, player ratings, fitness, morale, and potential.
- A starter transfer market with signings, transfer fees, squad sales, wage demands, free agents, and a 30-player squad cap.
- Player contracts with season lengths, renewal offers, signing bonuses, wage increases, expiry warnings, and free-agent departures at season rollover.
- Player playing-time tracking and morale dynamics: starting-XI selections build appearance records, regular starters gain morale, and underused players can become unhappy.
- Contract renewal negotiations: player morale and playing time influence acceptance, and unhappy players may require a larger wage offer.
- Incoming transfer bids from rival clubs for eligible senior players, with accept/reject controls and transfer-fee income.
- Paid scouting reports for transfer-market targets, revealing estimated potential and position-sensitive attributes (pace, passing, shooting, defending, and goalkeeping) before signing.
- Matchday payroll based on player ratings, wage-bill visibility, and a 5% wage increase at each new season.
- Recovery sessions, club funds, and upgradeable training, youth, and medical facilities.
- A youth academy with paid intakes, fictional prospects, development progress, and promotion into the senior squad.
- Gradual player development tied to age, potential, fitness, training focus, and training/youth facility levels.
- Local career save plus JSON export/import and multi-season progression.
- Progressive web app shell and GitHub Actions build workflow.

## Run locally

Requires Node.js 20 or newer.

```bash
npm install
npm run dev
```

Open the local URL printed by Vite. Build production files with:

```bash
npm run build
npm run preview
```

Vite writes the production app to `dist/`.

## Android plan

The first milestone is a working browser game. Android packaging with Capacitor comes after the core build is tested. A Play Store release will require an Android project, original app icons and screenshots, privacy/data disclosures, signing, and physical-device testing.

## Known prototype limits

- Match simulation is probabilistic, not a frame-by-frame tactical engine.
- Player attributes and tactical effects are simplified prototype models; they are not yet a full event-by-event tactical engine.
- Transfers and finances remain a prototype: wages are estimated from ratings and paid after each match; there are no release clauses, agents, player counter-offers, gate-receipt income, or AI club bidding.
- Clubs and players are fictional; there is no licensed real-world player data.
- Career saves live in the browser/device unless exported and imported.
- Offline support is an initial app-shell cache, not a guarantee that every feature works offline.
- No APK/AAB is included yet.

## Roadmap

1. Foundation: responsive UI, league loop, saves, build automation.
2. Simulation: attribute-driven match outcomes are now in place at prototype level; next improve substitutions, richer match analysis, and deeper injury types. Current injuries and discipline are lightweight matchday-availability prototypes.
3. Career: wage negotiations and counter-offers, release clauses, deeper scouting, staff, objectives, richer finances, and AI-driven transfer activity.
4. Quality: tests, balancing, accessibility, performance, original artwork.
5. Android: Capacitor integration, icons, device testing, signed release build.
6. Expansion: deeper tactical AI, African competitions, localization, PC-friendly controls.

## Principles

- Ship in tested milestones and don't claim unfinished features are complete.
- Use original or properly licensed artwork, data, and audio.
- Represent Ghanaian and African football meaningfully within a global football world.

## License

No license has been selected. All rights are reserved by default until one is added.

### Tactical substitution strategy

- Managers can select Balanced, Attack, or Protect Lead in match preparation.
- The match engine models up to three automatic tactical substitutions from minute 61 using available bench players. Attack prioritizes late attacking pressure; Protect Lead prioritizes defensive resistance; Balanced provides a smaller general boost.
- Substitutions are currently an automated match simulation model, not a manual pause-and-substitute live match interface.


### Custom starting XI

The tactics screen now lets the manager select each starting position instead of relying only on automatic selection. Lineup choices are saved with the career, are checked against position compatibility, and exclude injured or suspended players. When changing formations, any incompatible selection falls back to the best available player for that role.


### Match ratings and player of the match

After each fixture, the match report shows performance ratings for the selected starting XI, goals credited to starters where the event log identifies the scorer, and a player-of-the-match award. Ratings are a lightweight simulation based on player ability, fitness, morale, result, goals, and match variance; they are not real-world performance data.


### Season performance statistics

The manager dashboard and first-team squad page now aggregate player appearances, goals recorded in match reports, average match ratings, best rating, and season totals from the current season history. These stats are derived from the game simulation; only starting players currently receive individual ratings.


### Matchday presentation and dynamic transfer market

Match timelines now include a half-time score and a final-whistle summary, with distinct symbols for goals, cards, injuries, tactical substitutions, and the whistle. The transfer market evolves after matchdays: rival clubs may sign available targets, new fictional players can enter the market, and market changes are surfaced in the manager notification. These are lightweight simulated market events rather than a live online transfer network.
