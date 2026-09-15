# Debrief design system

Work-session logger. Log category, duration, what you did, mood 1–5, optional reason chips, notes. Dashboard: hours, streak, avg mood, session count, weekly chart, category progress cards (Coding / Cyber / School / Other), activity heatmap, mood line, recent sessions.

Pair with `wireframes.html` (interactive prototype). Lawson writes Next.js later. Web first. Clerk later.

## Tokens

- Background `#0B1628` `--bg`
- Sunken `#091322` `--bg-sunken`
- Surface `#12203A` `--surface`
- Raised `#162744` `--surface-2`
- Hover `#1A2E4E` `--surface-hover`
- Border `#243656` `--border`
- Subtle `#1C2C48` `--border-subtle`
- Text `#E7EDF6` `--text`
- Secondary `#A7B4C8` `--text-secondary`
- Muted `#7B8BA3` `--text-muted`
- Primary `#2F80ED` `--primary` — **one accent only**
- Primary dark `#1F6FD6` `--primary-dark`
- Primary soft `rgba(47, 128, 237, 0.14)` `--primary-soft`
- Danger `#C85A5A` `--danger`
- Success `#3BA88C` `--success`

Categories (same navy/blue family, not a second palette): Coding `#2F80ED`, Cyber `#5B8FA8`, School `#6A9EC7`, Other `#7B8BA3`.

Mood: 1 Rough `#C85A5A` · 2 Off `#8A9BB0` · 3 Steady `#7A93B0` · 4 Good `#2F80ED` · 5 Sharp `#3BA88C`.

Radius: chips 10px, inputs 12px, cards 16px (14–20), landing frame 20px. **8pt grid** (8/16/24/32/40/48/64/96). 1px borders. No glow, no purple/orange/yellow gradients, no shadows — border + one background step.

Type: Segoe UI / system-ui. Weights 400/500/600. Display 40, H1 28, H2 18, body 15, label 13, small 12, stat 28. Tabular nums on hours.

## Components

- Buttons: primary fill `#2F80ED` hover `#1F6FD6`; secondary 1px border; danger text+border; no gradient.
- Inputs 40px, sunken fill, primary focus ring (3px soft, no blur glow).
- Mood picker: **56px** squares, 1–5, then optional reason chips (Focused, Flow, Stuck, Tired, Interrupted, Rushed), then notes.
- Streak chip: `{n}-day streak`, primary-soft pill, 8px disk, no flame.
- Category cards: name, hours, thin progress vs week total.
- Heatmap: 12×7, primary opacity steps only.
- Empty: clipboard icon + “No sessions yet” + one CTA **Log your first session**.

## Pages

1. **Landing** — left hero “Close the day. Keep the record.” Get started / Sign in. Three points. How it works.
2. **Sign in** — Clerk placeholder, 400px card, email + Continue + Google/GitHub.
3. **Dashboard** — streak chip; hero hours/streak/avg mood/session count + weekly bars; 4 category cards; heatmap + mood line; recent table.
4. **New session** — date, duration (h+m), category chips, what you did, large mood, reason chips, notes. Save / Cancel.
5. **Sessions** — search, category, mood, range; table; row → detail.
6. **Detail** — view/edit in place; delete confirm.

App shell: 220px sidebar (Dashboard, Sessions, Log session, LH chip), 32px main padding.

Suggested Next.js routes: `/` `/sign-in` `/dashboard` `/sessions` `/sessions/new` `/sessions/[id]`.

Open the prototype: `design/wireframes.html`
