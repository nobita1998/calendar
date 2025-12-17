# Repository Guidelines

## Project Structure & Module Organization
- Static web app with a single entry point: `index.html` (HTML + inline CSS + inline JS for calendar logic and simple network tracking).
- If splitting code, prefer flat folders at the repo root: `styles/`, `scripts/`, `assets/` (e.g., `assets/images/`). Keep paths relative, no build system.
- Example files: `styles/calendar.css`, `scripts/analytics.js`, `assets/images/icon.png`.

## Build, Test, and Development Commands
- Run locally: `python -m http.server 8000` then open `http://localhost:8000/`.
- Alternatives: `npx serve` or VS Code “Live Server”.
- Optional format pass for small edits: `npx prettier --write index.html` (avoid mass reflow on large diffs).

## Coding Style & Naming Conventions
- Indentation 2 spaces; UTF‑8; aim for ~100‑char lines.
- HTML5 semantics and logical headings.
- CSS: kebab‑case classes (e.g., `.calendar-container`); group related rules; reuse colors/gradients.
- JS: camelCase (`changeMonth`, `updateCalendar`); small focused functions; avoid leaking globals.
- Filenames: lowercase with hyphens (e.g., `styles/calendar.css`).

## Testing Guidelines
- Manual checks: month navigation works, “today” highlight renders, unlock badges/notes align with dates, and no console errors.
- Cross‑browser: verify latest Chrome/Firefox/Edge.
- Responsive: confirm layouts at ~768px and ~480px.
- Accessibility: tab order, visible focus styles, color contrast, and `aria-label` for interactive controls.
- No automated tests configured; add only if scoped and low‑overhead.

## Commit & Pull Request Guidelines
- Commits: concise, imperative mood; group related changes. Example: “Fix month rollover edge case”.
- PRs: include a summary, before/after screenshots (desktop + mobile), test steps, and linked issues.
- Keep diffs minimal; avoid drive‑by refactors and mass formatting.

## Security & Configuration Tips
- External calls in `index.html` hit a counter API. Do not commit secrets; prefer anonymous endpoints or a proxy.
- Review third‑party resources; pin versions and document the source.

## Analytics
- Vercel Web Analytics is loaded via `scripts/analytics.js`.
- Include on each HTML page: `<script src="scripts/analytics.js" defer></script>` before `</body>`.
- The loader injects `/_vercel/insights/script.js` only on deployed domains (skips localhost).

## Agent‑Specific Instructions
- Make targeted edits; do not restructure unless necessary.
- If introducing `styles/`, `scripts/`, or `assets/`, update paths in `index.html` and this guide in the same change.

