# Osman — Training Block

A single-page web app for the Sam Samouy transformation block (June 2026).
Training log, meal checklist, cardio and lower back rehab. No login, no server —
everything is stored in the browser on the device that logged it.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app: markup, styles, plan data and logic |
| `manifest.webmanifest` | Makes it installable to the home screen |
| `icon-180.png` | iOS home screen icon |
| `icon-192.png` | Android home screen icon |
| `icon-512.png` | Splash / high-DPI icon |

All five go in the **root** of the repository. Paths inside the app are relative,
so it works whether the site is served from a domain root or from `/repo-name/`.

## Publishing

1. Upload all five files to the repo root.
2. Settings → Pages → Source: `main` branch, `/ (root)`.
3. Wait about a minute, then open the published URL.

## Installing on a phone

Open the URL in **Safari itself** (not a link inside WhatsApp or Instagram —
in-app browsers cannot create home screen icons), then Share → Add to Home Screen.

## First run

Open **More → Block position** and set the week and day Osman is actually on.
Every other number in the app — the day's session, the cardio target, the dots —
is worked out from that one setting and advances on its own after that.

## Changing the plan

The whole coaching document lives in one `PLAN` object near the top of the
`<script>` in `index.html`. Meals, exercises, macros, cardio and the split are
all in there. Nothing below that object needs editing to change the plan.

A `selfCheck()` runs on every load and warns in the browser console if the plan
data is malformed — an empty block, an exercise with neither reps nor a hold, a
supplement pointing at a meal that does not exist.

## Cached copies

Every build carries a tag, shown at the bottom of the Today and More tabs.
This one is `2026-07-22-osman-E`. If the page shows anything else after you
push, you are looking at a cached copy — hard refresh, or add `?v=2` to the URL.
