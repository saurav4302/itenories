# Goa Trip Planner — Photo Memories

## Plan
- [x] Add a Photos menu and gallery page.
- [x] Add camera/library upload input to each itinerary activity.
- [x] Store photos locally in the browser and link them to the activity location.
- [x] Add full-screen viewing and an explicit Save to phone action.
- [x] Keep the activity cleanup behavior intact.
- [x] Add Google Drive connection, OAuth sign-in, folder creation, and photo upload sync.
- [x] Keep local browser storage as a fallback when Drive is not connected.

## Verify command
```text
awk '/<script>/,/<\/script>/' "/Users/binarybrain/Documents/ChatGPT/Trip To GOA/index.html" | sed '1d;$d' > /tmp/goa-js.js && node --check /tmp/goa-js.js
```

## Evidence
- `node --check /tmp/goa-js.js` passed with no output.
- `git diff --check` passed.
- Feature checks passed: Photos navigation, photo page, camera input, IndexedDB storage, photo gallery, Save to phone, and itinerary photo buttons.
- Drive checks passed: Drive status card, OAuth PKCE flow, Drive folder creation, Drive upload API, local fallback, and location metadata.
