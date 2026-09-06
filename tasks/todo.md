# Goa Trip Planner — Photo Memories

## Plan
- [x] Add a Photos menu and gallery page.
- [x] Add camera/library upload input to each itinerary activity.
- [x] Store photos locally in the browser and link them to the activity location.
- [x] Add full-screen viewing and an explicit Save to phone action.
- [x] Keep the activity cleanup behavior intact.
- [x] Add Google Drive connection, OAuth sign-in, folder creation, and photo upload sync.
- [x] Keep local browser storage as a fallback when Drive is not connected.
- [x] Keep the photo dialog centered on phone screens and preserve the Google Client ID in the default configuration.

## Verify command
```text
awk '/<script>/,/<\/script>/' "/Users/binarybrain/Documents/ChatGPT/Trip To GOA/index.html" | sed '1d;$d' > /tmp/goa-js.js && node --check /tmp/goa-js.js
```

## Evidence
- `node --check /tmp/goa-js.js` passed with no output.
- `git diff --check` passed.
- Feature checks passed: Photos navigation, photo page, camera input, IndexedDB storage, photo gallery, Save to phone, and itinerary photo buttons.
- Drive checks passed: Drive status card, OAuth PKCE flow, Drive folder creation, Drive upload API, local fallback, and location metadata.
- Live browser check reached the deployed Photos page, Google account chooser, and the standard Testing-app warning with the configured Drive Client ID and redirect URI.
- Replanned itinerary now uses Skyi Songbirds → Lotus Sutra/Arambol for Sept 10–12 → The Nautical Nest/Palolem for Sept 12–14 → direct South Goa-to-Pune drive on Sept 14.

## Flashy Timeline Animation — 2026-09-06

### Plan
- [x] Replace static hero gradient with 4-image crossfade slideshow + indicator dots.
- [x] Add staggered day-card reveal (cubic-bezier, slide-up + fade).
- [x] Add staggered activity reveal (slide-in from left + fade).
- [x] Add glowing left-rail on each activity that brightens on hover.
- [x] Add hover lift + soft shadow on activities and day cards.
- [x] Add ripple/pulse on the activity checkbox when marked done.
- [x] Add row flash + stat-card flash when marking done.
- [x] Add animated shimmer on the day progress fill.
- [x] Add prefers-reduced-motion override that disables every animation.
- [x] Keep mobile-friendly sizing and reduced-motion fallback.
- [x] Wire `--day-index` and `--item-index` from JS for stagger timing.
- [x] Auto-advance hero indicator dots in sync with slideshow timing.

### Verify command
```text
awk '/<script>/,/<\/script>/' "/Users/binarybrain/Documents/ChatGPT/Trip To GOA/index.html" | sed '1d;$d' > /tmp/goa-js.js && node --check /tmp/goa-js.js
```

### Evidence
- `node --check /tmp/goa-js.js` passed with no output.
- `git diff --check` passed.
- Confirmed presence via grep: `heroFade`, `dayReveal`, `activityReveal`, `progressShimmer`, `ripple`, `checkPulse`, `rowFlash`, `statFlash` each appear twice (definition + usage); `prefers-reduced-motion` once; `data-activity-id` once; `activity-just-completed` 8x; `stat-flash` 5x; `day-index` 2x; `item-index` 2x; `hero-slide` 8x; `hero-indicators` 2x; `hero-dot` 3x.
- `setStatus` now triggers ripple + stat-card flash; `renderTimeline` sets `--day-index`; `renderActivity` accepts an `itemIndex` and sets `--item-index` plus `data-activity-id`.
