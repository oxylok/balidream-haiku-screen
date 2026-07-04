# Timing Log — balidream-haiku-screen

Experiment run for comparing model/effort configurations on the same task
(see [site-factory-task.md](site-factory-task.md)). Timestamps are git commit
times (local, +0200); the task-start reference point is the mtime of the
brief materials dropped into this folder.

| Event | Timestamp | Elapsed |
|---|---|---|
| Task materials placed in folder (BaliDream.jpg, Cover.jpg, brief, guide) | 01:59:11 | — |
| First commit — full index.html built (verstka) | 02:13:45 | **+14m 34s** |
| Self-check report + GH Actions workflow | 02:17:58 | +4m 13s |
| Deployment guide (docs) | 02:19:06 | +1m 08s |
| Delivery report (docs) | 02:20:09 | +1m 03s |
| Quickstart guide (docs) | 02:20:52 | +0m 43s |
| Project summary (docs) | 02:23:39 | +2m 47s |
| **Turn boundary** — user said "сделай это сам" (deploy on Vercel) | — | — |
| GitHub repo created + pushed, Vercel CLI installed, authenticated, deployed to production, deployment doc committed | 02:28:08 | **+4m 29s** |

## Summary

- **Build (verstka) — materials → working site + self-check + docs:**
  01:59:11 → 02:23:39 = **~24.5 minutes**
  - Of which pure markup (materials → first working `index.html` commit): **~14.5 minutes**
  - Remainder (~10 min): self-check pass (responsive/contrast/links/SEO in browser preview) + writing docs
- **Deploy (GitHub + Vercel, separate turn):** **~4.5 minutes**
  - `gh repo create` + push, `npm install -g vercel`, `vercel login` (device flow), `vercel --prod`
- **Total, task-materials-to-live-URL:** **~29 minutes**

## Caveats for cross-run comparison

- These are git-commit timestamps, not wall-clock task-start/end — there's
  inherent slack (e.g. time spent reading images/reasoning between commits
  isn't separately logged). Treat as an approximation, consistent in method
  across the parallel experiment folders as long as each run also commits
  incrementally.
- The deploy phase here reused an already-authenticated `gh` CLI; a run
  without prior GitHub auth would need to add that step's time.
- Model/effort for this run: both the build phase and the deploy phase were
  done with Claude Fable 5 (`claude-fable-5`). The `/model` switch to
  `claude-sonnet-5` happened afterward, only for writing this timing log.
