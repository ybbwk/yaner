# Changelog

## v0.3.2 (2026-10-12)

- Fixed: creating a task always failed with "Unauthorized" — the aria2c RPC token was placed last in the parameter array and failed authentication
- Fixed: an aria2c left behind after a crash could never be reclaimed, so the occupied port prevented all later downloads
- Fixed: "Software License" and "Open Source License" in the About dialog reported a missing file
- Fixed: license files were named inconsistently between the MSI and NSIS installers
- Fixed: a blank terminal window flashed when playing the completion sound
- Fixed: double-clicking a finished task or using the right-click "Open" reported "Windows cannot find the file"
- Fixed: "Paste" in the text field context menu did nothing
- Fixed: trackpad two-finger scrolling produced a web-style rubber band effect at the edges
- Fixed: a terminal window flashed before the browser opened from the About dialog
- Improved: website, software license and open source license are now plain hyperlinks in the About dialog
- Improved: text fields use a custom context menu that no longer exposes browser developer tools
- Improved: added an "Open Website" entry to the About dialog
- Improved: update check results are shown on the About page directly, without an extra dialog
- Maintenance: corrected the option types sent to aria2 (`auto-file-renaming`, `bt-stop-timeout`); automatic renaming of same-named files may not have taken effect before

## v0.3.1 (2026-10-12)

- Fixed: UPnP port mapping could block task creation for up to 200 seconds on networks without a UPnP router
- Fixed: UPnP cleanup during exit could exhaust the budget, leaving aria2c running
- Fixed: aria2c graceful-exit budget was counted per port, reaching up to 9 seconds
- Fixed: closing the BT dialog while confirming would delete the task just created
- Improved: UPnP port mapping is now asynchronous and no longer delays task creation
- Improved: download engine is prewarmed at startup, so creating a task no longer waits for it
- Improved: only the confirm button is disabled during submission, with a loading indicator; the dialog stays closable
- Improved: shutdown cleanup is idempotent and unified across tray, menu bar and the exit command
- Improved: aria2c readiness probe now checks before waiting, removing one poll interval from cold start
- Maintenance: no longer delete mappings this run never created, avoiding removal of other apps' rules on the same ports

## v0.3.0 (2026-10-06)

- Added: bottom status bar showing engine state, RPC port, BT listen port, UPnP mapping result and live speed
- Added: download engine RPC port and BT/DHT listen port are configurable, with automatic fallback when occupied
- Added: the "new version available" notice itself is clickable and opens the download page in the system browser
- Fixed: app completely unusable when the engine port was already in use
- Fixed: unreliable aria2c engine startup and shutdown
- Fixed: download confirm button double-submit creating duplicate tasks
- Fixed: magnet link / torrent preview unable to parse the file list
- Fixed: saving settings silently disabled "shut down after download" and reset unexposed config such as database path
- Fixed: download/upload speed limits never reached the engine
- Fixed: tasks showed "downloading" even when the engine failed to start
- Fixed: deleting a task could remove control files of other tasks sharing the same directory
- Fixed: magnet metadata wait was a fixed 30s with indistinguishable errors; now 15s with graded messages
- Fixed: mirror discovery had no timeout and could block task creation
- Improved: opening a download link on Windows no longer flashes a console window
- Maintenance: dropped unused gRPC dependencies (tonic/prost), declared MSRV, committed Cargo.lock
- Maintenance: upgraded rusqlite / config / dirs / toml; frontend upgraded to React 19 and Vite 8

## v0.2.0 (2026-09-20)

- Added: UPnP port mapping — automatically open router ports for faster BT downloads
- Added: Mirror discovery — find mirrors for the same file and download from multiple sources
- Fixed: magnet link / torrent preview unable to parse file list
- Fixed: shutdown countdown reaching zero but not executing shutdown
- Fixed: Windows command window flashing when manually shutting down
- Improved: shutdown timer moved to backend — works even when window is closed

## v0.1.3 (2026-08-06)

- Fixed: error when opening completed tasks
- Improved: persist real download path in database, opening/deleting files stays accurate after restart

## v0.1.2 (2026-08-04)

- Added: double-click to run completed tasks; "Open" item in context menu
- Added: startup splash screen to eliminate white flash
- Fixed: multiple tray icons when launching repeatedly on Windows
- Fixed: macOS build failure
- Dependency updates

## v0.1.1 (2026-08-02)

Fixed database init on fresh install

## v0.1.0 (2026-07-27)

Initial release.
