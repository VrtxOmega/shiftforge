# SHIFTFORGE

**Smart employee shift scheduler with compatibility-aware optimization — all data stays in your browser.**

[![VERITAS](https://img.shields.io/badge/VERITAS-%CE%A9-gold.svg?style=for-the-badge&colorA=000000&colorB=d4af37)](https://github.com/VrtxOmega)
[![Status](https://img.shields.io/badge/Status-ACTIVE-success?style=for-the-badge&labelColor=000000&color=d4af37)](https://vrtxomega.github.io/shiftforge/)
[![Stack](https://img.shields.io/badge/Stack-Vanilla%20JS%20%2B%20GitHub%20Pages-informational?style=for-the-badge&labelColor=000000)](https://github.com/VrtxOmega/shiftforge)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge&labelColor=000000)](LICENSE)

**Live Site:** https://vrtxomega.github.io/shiftforge/

---

## OVERVIEW

ShiftForge is a browser-based employee scheduling tool that auto-generates optimized weekly shift schedules. It factors in employee availability, team compatibility ratings, role coverage requirements, fair hour distribution, and individual strengths — then produces a conflict-free schedule in one click. Built for real restaurant operations. Validated against 6 weeks of simulated shift data across all shift types and role configurations.

All data is stored locally in the browser. No server. No accounts. No tracking.

---

## FEATURES

- **Auto-Generate Schedules** — Constraint-aware algorithm optimizes for availability, compatibility, role coverage, fair distribution, and employee strengths simultaneously.
- **Team Compatibility Matrix** — Rate every employee pair from Conflict (avoid together) to Great (best pairing). The scheduler respects these ratings when building shifts.
- **Shift Configuration** — Define custom shift blocks (Morning, Lunch Rush, Dinner, Close) with start/end times. Applies across the full week.
- **Role Management** — Define positions (Line Cook, Prep Cook, Cashier, Shift Lead, Expeditor, Drive-Thru) so the scheduler ensures proper coverage per shift.
- **Employee Availability** — Set per-employee availability windows so the algorithm never schedules someone when they can't work.
- **Preset Traits** — Quick-assign personality, strength, and weakness tags when adding employees. Personality presets include Leader, Team Player, Independent, Calm, Detail-Oriented. Strength presets include Speed, Accuracy, Customer Service, Food Prep, Cash Handling. Weakness presets include Tardiness, Phone Usage, Slow Under Pressure.
- **Schedule Constraints** — Configure min/max employees per shift, max shifts per week per person, and priority mode (Balanced, Seniority, Availability).
- **Dashboard Overview** — At-a-glance stats: employee count, shift types, good pairings, conflicts flagged, roles defined, availability set.
- **Zero Infrastructure** — Pure client-side. All data persisted in browser localStorage. Deploy anywhere as a static site.

---

## ARCHITECTURE

```
┌─────────────────────────────────────────────────┐
│                  SHIFTFORGE                     │
│           Client-Side Web Application           │
└────────────────────┬────────────────────────────┘
                     │
         ┌───────────┼───────────┐
         ▼           ▼           ▼
  ┌────────────┐ ┌──────────┐ ┌──────────────┐
  │  Schedule  │ │   Data   │ │     UI       │
  │  Engine    │ │  Store   │ │   Layer      │
  │            │ │          │ │              │
  │ Constraint │ │ Browser  │ │  Dashboard   │
  │ Solver     │ │ Local    │ │  Employees   │
  │ Compat.    │ │ Storage  │ │  Availability│
  │ Optimizer  │ │          │ │  Compat.     │
  └────────────┘ └──────────┘ │  Settings    │
                               └──────────────┘
```

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Schedule Engine** | Vanilla JS | Constraint solver with compatibility, availability, and fairness optimization |
| **Data Store** | localStorage | All employee, shift, role, and schedule data persisted client-side |
| **UI Layer** | HTML / CSS / JS | 6-tab dashboard with VERITAS gold-and-obsidian aesthetic |
| **Deployment** | GitHub Pages | Static hosting, zero server dependency |

---

## VALIDATION

The scheduling algorithm was validated against **6 weeks of simulated shift data** covering all shift types (Morning, Lunch Rush, Dinner, Close), all role configurations, and edge cases including:

- Employees with overlapping availability restrictions
- Conflicting compatibility pairs forced into limited shift pools
- Maximum shift cap enforcement across full weeks
- Role coverage minimums under constrained employee counts

---

## QUICKSTART

No installation required. Open the live site and start adding employees:

1. **Configure shifts and roles** in the Settings tab
2. **Add employees** with availability, roles, and traits
3. **Set compatibility** ratings between employee pairs
4. **Generate Schedule** — the algorithm handles the rest

Or run locally:

```bash
git clone https://github.com/VrtxOmega/shiftforge.git
cd shiftforge
# Open index.html directly, or serve with any static server
npx serve .
```

---

## SECURITY & PRIVACY

- **No server.** Zero backend. Zero API calls. Zero cloud.
- **No tracking.** No analytics, no telemetry, no cookies beyond localStorage.
- **No accounts.** No sign-up, no authentication, no data leaves the browser.
- **Your data stays yours.** All employee and schedule data lives exclusively in your browser's localStorage.

---

## LICENSE

MIT — see [LICENSE](LICENSE) for full terms.

---

Built by [RJ Lopez](https://github.com/VrtxOmega) — VERITAS & Sovereign Ecosystem
