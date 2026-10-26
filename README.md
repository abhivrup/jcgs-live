# JCGS YouTube App
GitHub Pages build: https://abhivrup.github.io/jcgs-live/

## App metrics (private)
- Opens dashboard (Google Sheet): https://docs.google.com/spreadsheets/d/1MGqPdhoOPMqwgVSoFXZD_EvmNl9j8fKLsQOWn8WDLqU/edit

## Releases

### v1.7 — Oct 25, 2026 (current production) — tag `v1.7`, commit a84ec06

**Change set since v1.6:**
- External links: fixed the blank in-app browser sheet left behind when returning from an external link in the Home Screen app. External opens (YouTube menu item, Live error fallback, Playlists web fallback) now navigate directly when the app runs standalone, so iOS hands the link to the system and no blank sheet remains; in a normal browser tab they still open in a new tab.
- Version: header and the app-open counter now report v1.7.

### v1.6 — Oct 25, 2026 — tag `v1.6`, commit eb12745

**Change set since v1.5:**
- Videos: the menu item now opens a browsable list of the channel's latest uploads, mirroring JCGS Events — titles load in the background, only titled videos get a row (no blank rows), and selecting one plays it at its uploads-playlist index (wheel Next/Previous still steps through in order). Fallbacks mirror Events (autoplay from the start if harvest/title lookup fails). Previously Videos just autoplayed the uploads playlist with no way to pick a video.
- Version: header and the app-open counter now report v1.6.

### v1.5 — Oct 25, 2026 — tag `v1.5`, commit 5db6dbc

**Change set since v1.4:**
- Playback: removed the app's own Full Screen button and the fullscreen machinery behind it (element-fullscreen helpers, pseudo-fullscreen fallback and its MENU exit path, and their styles). The Now Playing screen now shows only the title, subtitle and progress bar — no buttons at all. On iPhone the button could never give true fullscreen anyway (only YouTube's own in-player button can, and it still works — the embed's fullscreen permissions are unchanged). Completes the playback cleanup begun in v1.4.
- Version: header and the app-open counter now report v1.5.

### v1.4 — Oct 25, 2026 — tag `v1.4`, commit e71c211

**Change set since v1.3:**
- Playback: removed the app's own two "Watch on YouTube" buttons — the labeled button on the Now Playing screen and the floating shortcut shown during fullscreen — along with their click handlers, helper function and styles. The Full Screen button now stands alone on the Now Playing screen. The menu's YouTube item and Live Darshan's automatic error fallback to YouTube are unchanged. (Experiment — can be reverted to v1.3.)
- Version: header and the app-open counter now report v1.4.

### v1.3 — Oct 25, 2026 — tag `v1.3`, commit dc5a920
Change set since v1.2:
- **JCGS Events** — only events whose titles have loaded are shown: no blank rows; the list opens on the most recent events with the selection on the first event, and more rows appear as background title loading completes.
- **Version** — header and the app-open counter now report v1.3.

### v1.2 — Oct 25, 2026 — tag `v1.2`, commit c8cd134
Change set since v1.1:
- **Fixed: Live Darshan / Live Event** — YouTube's live_stream embed stopped resolving ("This video is unavailable"), so the app now resolves the channel's current live video ID at open time via an Apps Script endpoint and plays it through the standard embed; the previous behavior remains as fallback. (Commit eb805b9)
- **JCGS Events** — titles load silently in the background: the 10 most recent events show immediately and the rest fill in without a "Loading…" label.
- **Header** — the battery icon is replaced by the app version (v1.2), set by the APP_VERSION constant in index.html.
- **Metrics** — the app-open counter now records the app version with each open, so the metrics dashboard shows opens by version.

### v1.1 — Oct 25, 2026 — tag `v1.1`, commit 4a1b61a
- Rollover (wrap-around) navigation in menus, lists and Now Playing (commit c389ec3).
- Private app-open counter: an invisible beacon to a Google Apps Script endpoint logging opens to a private Sheet (production vs test, daily counts).
- README created with the app-metrics Sheet link.

### GOLDEN v1 — Oct 25, 2026 (rollback point) — tag `golden-v1`, commit d4eee89
- The known-good baseline: menu "Live Darshan / Live Event · JCGS Events · Reels · Playlists · Videos · YouTube · Now Playing"; Home Screen name "JCGS".
