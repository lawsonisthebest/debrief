# Debrief design

This folder is the visual source of truth for **Debrief** before any Next.js code is written.

Lawson Higgins implements the app later in Next.js. Do not treat these files as application source. There is no `src/` here on purpose.

## Files

| File | What it is |
| --- | --- |
| `DESIGN.md` | Product summary, color tokens, type, spacing, component inventory, and page-by-page layout notes |
| `wireframes.html` | Self-contained mid-fidelity desktop mockups of all six pages (real palette, sample data) |
| `README.md` | This file |

## Open the wireframes

`wireframes.html` has **no external dependencies** (no CDN, no webfonts, no JS libraries). Open it locally:

1. In File Explorer go to `C:\\Users\\lawso\\OneDrive\\Desktop\\Projects\\debrief\\design`
2. Double-click `wireframes.html`, or right-click → Open with → Microsoft Edge / Chrome
3. Or from PowerShell:
   ```powershell
   start C:\\Users\\lawso\\OneDrive\\Desktop\\Projects\\debrief\\design\\wireframes.html
   ```

The page is a wireframe viewer: switch the six screens with the top tabs, or choose **Stack all** to scroll every 1280px frame.

Designed at **~1280px** desktop width. The frames are 1280px wide; zoom the browser if your window is smaller.

## What to build from

Use `DESIGN.md` for tokens and behavior, and `wireframes.html` for structure, hierarchy, and density. Sample sessions in the mockups are **example data**, labeled as such.

Auth is a **Clerk placeholder layout** only — not a working sign-in.

## Implementation later

Next.js (App Router) will live in this same repo when Lawson starts coding. Until then, keep product UI work in `design/`.
