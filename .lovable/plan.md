# Import & Improve StoryQuest AI

## What I found in your repo
- **StoryQuest AI** — an interactive AI story app (landing page, Create Story, story player with checkpoints, My Stories, Profile, Learning Report, sign-in).
- Built with React + TanStack Start + Tailwind + shadcn — the same stack as this project, so it imports cleanly.
- Roadmap shows Phases 1–4 done; Phase 5 (final quality pass + publish) is unfinished.

## Plan

### Step 1 — Import the code
- Copy the app's pages, components, story engine, styles, and images from the repo into this project.
- Keep the local-first story store working without a backend so the app runs immediately.
- Skip the repo's `.env` (contains keys — I won't copy secrets into code).

### Step 2 — Get it running
- Fix any import/build issues, verify every page loads: Home, Create, Story player, My Stories, Report, Profile, About, Auth.
- Replace the placeholder home page with your real landing page.

### Step 3 — Improvements pass
- **Design polish:** tighten spacing, typography, and mobile layout; smoother page transitions and story-player interactions.
- **Bug fixes:** run the existing tests, fix anything broken in the playthrough flow (create → play → checkpoints → report).
- **Small feature wins** (pick after import): e.g. story sharing link, progress badges, better empty states, loading skeletons.

### Step 4 — Verify & hand off
- Full playthrough test in the preview, then you can publish.

## Notes
- Your original Lovable project stays untouched — this is a copy we improve here.
- Sign-in/cloud sync from the old project won't carry over automatically; the app works local-first, and we can re-enable accounts later if you want.
- Tell me any specific improvements you already have in mind and I'll fold them into Step 3.
