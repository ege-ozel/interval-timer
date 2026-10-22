# Session Followup

You're picking up work on the `interval-timer` repo (Electron desktop app
+ installable PWA; GitHub: `ege-ozel/interval-timer`, formerly
`psymore/interval-timer`). Updated by Claude whenever the user asks for a
followup summary, or at a natural session-end point. Read this file fully
whenever the user types `FOLLOWUP` — whether that's later in the same
session or the very first message of a brand-new one with no other context
loaded. If this is a fresh session, read `CLAUDE.md` first for the
architecture, then come back here for current status. Either way, pick up
exactly where this left off rather than asking what to do or re-deriving
context from scratch — continue with whatever "Likely next steps" below
says is next, asking which one only if more than one applies and it isn't
obvious.

**Last updated:** 2026-10-23

## Summary

This session (2026-10-23) shipped **v1.1.1**:

- Mobile top bar fix in `packages/core/css/styles.css` (inside the
  `max-width: 440px` block): icons on their own row above full-width tabs,
  icon buttons no longer inflated by the generic `button { min-width: 70px }`
  rule, Quit is icon-only on phones. Synced to `docs/app` and `docs/pwa`.
- Landing-page demo (`docs/assets/mini-demo.js`) now opens expanded (full
  app view) on every viewport, phones included; mobile caption updated in
  EN/TR (`docs/assets/i18n.js`, `docs/index.html`).
- Version bumped to 1.1.1 in all package.json files, tag `v1.1.1` pushed,
  GitHub Release published with `Interval.Timer.Setup.1.1.1.exe` (marked
  latest), and installed on the user's machine.
- Then shipped **v1.1.2** the same way: app title renamed from "Timer
  App" to "Interval Timer" (heading, `<title>`, tray tooltip, EN + TR);
  released, marked latest, and installed here.
- Local `origin` remote repointed to `https://github.com/ege-ozel/interval-timer.git`.
  The live site is at `https://ege-ozel.github.io/interval-timer/`.

## Open items

- **Landing-page demo icon problem on a real phone** — the user's phone
  screenshot showed the *old* overflowing top bar (pre-v1.1.1, likely
  cached), so this is probably already fixed. Confirm with the user after
  a refresh on their phone.
- **Old `psymore` links** — README, `docs/index.html` (links, downloads
  badge, giscus `data-repo`) and `packages/electron/lib/updateChecker.js`
  (`REPO`) still say `psymore/interval-timer`. github.com redirects, but
  `psymore.github.io` likely does not. Do NOT change `appId`
  (`com.psymore.intervaltimer`) — it would break existing installs.
- **`npm version` / npm install wipes the Electron binary** — npm's
  install-script allowlist blocks `electron`'s postinstall; restore with
  `node node_modules/electron/install.js` (with `ELECTRON_RUN_AS_NODE` unset).
- `.claude/launch.json` (local static-server previews for `docs/` and
  `packages/core`) is untracked on purpose.
- Older items still open: mobile app brainstorm, stale `worktree-agent-*`
  branches, Dependabot alert confirmation (now possible — `gh` is installed
  and authenticated).

## Likely next steps

- Fix the demo icon issue once the screenshot arrives (own branch — landing
  page work never goes on an app feature branch).
- Update the `psymore` links to `ege-ozel` on a new branch.
