# Debrief — Firestore schemas

Path style: `users/{userId}/sessions/{sessionId}`

---

## Collection: `users`

| Field | Type | Required | Notes |
|---|---|---|---|
| `displayName` | string | no | optional profile label |
| `email` | string | no | if you store it from auth |
| `createdAt` | timestamp | yes | account/doc created |
| `updatedAt` | timestamp | yes | last profile update |

---

## Collection: `users/{userId}/sessions`

One document per logged work session.

| Field | Type | Required | Notes |
|---|---|---|---|
| `title` | string | yes | e.g. "Refactored auth middleware" |
| `category` | string | yes | one of: `Coding`, `Cyber lab`, `School`, `Other` |
| `startedAt` | timestamp | no | when the session started |
| `endedAt` | timestamp | no | when the session ended |
| `durationMinutes` | number | yes | integer minutes |
| `mood` | number | yes | integer 1–5 |
| `notes` | string | no | freeform reflection |
| `projectTag` | string | no | e.g. "debrief-api" |
| `focusQuality` | string | no | e.g. `High`, `Medium`, `Low` |
| `reasons` | array of string | no | e.g. `["Focused", "Flow"]` — from: Focused, Stuck, Flow, Tired |
| `countTowardStreak` | boolean | yes | default `true` |
| `createdAt` | timestamp | yes | when the log was saved |
| `updatedAt` | timestamp | yes | last edit |

---

## Example session document

```json
{
  "title": "Refactored auth middleware",
  "category": "Coding",
  "startedAt": "2025-05-20T14:30:00Z",
  "endedAt": "2025-05-20T16:05:00Z",
  "durationMinutes": 95,
  "mood": 4,
  "notes": "Separated JWT validation from permission checks. Tests passing.",
  "projectTag": "debrief-api",
  "focusQuality": "High",
  "reasons": ["Focused", "Flow"],
  "countTowardStreak": true,
  "createdAt": "2025-05-20T16:10:00Z",
  "updatedAt": "2025-05-20T16:10:00Z"
}
```

---

## What powers each screen

- **New session / Session detail / Sessions list** → `sessions` documents
- **Dashboard KPIs** (hours, session count, avg mood) → computed from `sessions`
- **Streak** → computed from `sessions` where `countTowardStreak` is true (by day)
- **Category breakdown** → sum `durationMinutes` grouped by `category`
