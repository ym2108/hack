# Video Studio

Two video engines live here:

- `remotion/` — Remotion (React/TS). Use the `remotion-*` skills. Register compositions in `src/Root.tsx`; render with `npx remotion render <Id> out/<name>.mp4`.
- `hyperframes/` — HyperFrames (HTML/GSAP). Start with the `/hyperframes` skill; see `hyperframes/CLAUDE.md`.

When the user gives a script, ask which engine they want if they haven't said; default to HyperFrames for quick motion-graphics/explainers and Remotion for data-driven or templated videos.

Rules:
- The sandbox network blocks CDNs (e.g. cdn.jsdelivr.net). Vendor any JS/CSS/fonts into `hyperframes/assets/` (pull from npm via `npm pack`) instead of linking a CDN.
- Chrome comes from `REMOTION_BROWSER_EXECUTABLE` / `HYPERFRAMES_BROWSER_PATH` (set by the SessionStart hook). Don't run `npx hyperframes browser ensure` or let Remotion download Chrome in the cloud.
- Render outputs go in `out/` (gitignored). Commit source, not MP4s, unless asked.
