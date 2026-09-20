# Changelog

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
