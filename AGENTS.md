# Repository Guidelines

## Project Structure & Module Organization
- Static web app with a single entry point. The main file is `index.html` and includes HTML, inline CSS, and inline JS (calendar logic + simple network tracking).
- If you split code, prefer `styles/`, `scripts/`, and `assets/` (e.g., `assets/images/`). Keep paths relative to repo root.
- Keep structure flat and minimal; avoid unnecessary folders or build systems.

## Build, Test, and Development Commands
- Run locally: `python -m http.server 8000` then open `http://localhost:8000/`.
- Alternative local servers: `npx serve` or use VS Code “Live Server”.
- Optional format pass for small edits: `npx prettier --write index.html` (avoid mass reflow in large changes).

## Coding Style & Naming Conventions
- Indentation: 2 spaces; UTF‑8; aim for ~100‑char lines.
- HTML5: use semantic tags and a logical heading hierarchy.
- CSS: kebab‑case classes (e.g., `.calendar-container`); group related rules; reuse colors/gradients consistently.
- JS: camelCase for variables/functions (e.g., `changeMonth`, `updateCalendar`); small, focused functions; avoid leaking globals.
- Filenames: lowercase with hyphens (e.g., `styles/calendar.css`).

## Testing Guidelines
- Manual checks: month navigation works, “today” highlight renders, unlock badges/notes align with dates, and no console errors.
- Cross‑browser: verify latest Chrome/Firefox/Edge.
- Responsive: confirm layouts at ~768px and ~480px.
- Accessibility: tab order, visible focus styles, color contrast, and `aria-label` for interactive controls.
- No automated tests configured; add only if scoped and low‑overhead.

## Commit & Pull Request Guidelines
- Commits: concise, imperative mood (e.g., “Fix month rollover edge case”); group related changes.
- PRs: include a summary, before/after screenshots (desktop + mobile), test steps, and linked issues.
- Keep diffs minimal; avoid drive‑by refactors and mass formatting.

## Security & Configuration Tips
- External calls in `index.html` hit a counter API. Do not commit secrets; prefer anonymous endpoints or a proxy.
- Review any third‑party resources; pin versions and document the source.

## Analytics
- Vercel Web Analytics is integrated via a shared loader at `scripts/analytics.js`.
- Each HTML page should include `<script src="scripts/analytics.js" defer></script>` before `</body>`.
- The loader injects `/_vercel/insights/script.js` only on deployed domains (skips localhost) to avoid 404s in dev.

## Agent‑Specific Instructions
- Make targeted edits; do not restructure unless necessary.
- If introducing `styles/`, `scripts/`, or `assets/`, update paths in `index.html` and this guide in the same change.
