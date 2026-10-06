# Changelog

## v0.3.0 (2026-10-06)

- Added: bottom status bar showing engine state, RPC port, BT listen port, UPnP mapping result and live speed
- Added: download engine RPC port and BT/DHT listen port are configurable, with automatic fallback when occupied
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
