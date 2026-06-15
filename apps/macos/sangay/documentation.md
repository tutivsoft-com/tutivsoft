---
title: Sangay Free Space Monitor - Documentation
description: Complete user guide and documentation for Sangay Free Space Monitor.
permalink: /apps/macos/sangay/documentation/
---

# Sangay Free Space Monitor Documentation

## Overview

Sangay Free Space Monitor is a native macOS menu bar app for watching free disk space on your main system volume. It keeps current storage status visible in the menu bar, alerts you before space becomes critical, and gives you safe cleanup workflows plus large-item tools and storage history charts.

The app is intentionally conservative:
- It monitors the primary system disk only.
- Every manual cleanup run is previewed first.
- Manual cleanup runs only after a preview is generated.
- Automatic cleanup is enabled by default and limited to low-risk targets.
- Full Disk Access explanation appears only when you open cleanup, not on launch.

---

## Getting Started

### System Requirements
- macOS 14 or later
- Notification permission (if you want alert banners)
- Access to your own user folders for cleanup preview and scanning

### Launching The App
For a normal download, open the `.dmg`, drag `SangayFreeSpaceMonitor.app` to `Applications`, then open it from `Applications`.

When it starts:
- It requests notification permission.
- It begins monitoring disk space.
- It appears in the menu bar.
- It does not normally show a Dock icon.
- It does not ask for Full Disk Access unless you open the cleanup flow.

---

## Using Sangay

### Menu Bar Item
The menu bar label can be configured to show `Free %`, `Free GB`, `Used GB`, `Icon Only`, or `Status Dot`. The color reflects the current disk state (normal, warning, critical, emergency).

Click the menu bar item to open the main menu to refresh status, open the dashboard, review cleanup, manage alerts, or access settings.

### Dashboard
The dashboard window gives you a larger summary view, including:
- A free-space gauge and storage history chart (24-hour, 7-day, 30-day).
- Current alert state and refresh interval.
- Latest cleanup preview estimate and result.
- Latest large-item scan timestamp.

### Alerts
The app supports three alert levels: warning, critical, and emergency. Each level can be customized with threshold values (GB or %), notifications, and sounds. 

You can pause alerts from the menu bar. While paused, the active alert level is still shown in the UI, but notifications and sounds are suppressed.

---

## Safe Cleanup & Maintenance

### Cleanup Review
Manual cleanup is always review-first. When you run cleanup, the app builds a preview of items to be removed. You must confirm the preview before any files are deleted.

**Cleanup Presets:**
*   `Caches`, `Logs`, `Temporary Files`, `Trash`, `Developer Caches`

**Risk Labels:**
The preview groups targets by risk. `Low Risk` covers caches, logs, and temporary files. `Review Carefully` covers Trash and developer caches.

### Large-Item Tools
The cleanup view includes tools to scan your home folder for `Large Files` and `Largest Folders`. The scan walks your home directory recursively, skips symbolic links, and lists the largest items so you can reveal them in Finder.

### Scheduled Cleanup
Scheduled cleanup supports two behaviors:
- **Review First:** The app raises a prompt and waits for you to open Cleanup manually.
- **Auto Clean Safe Targets:** The app removes only low-risk targets automatically and leaves higher-risk targets for review.

Schedules can be set to Daily, Weekly, or When Below Threshold.

---

## Troubleshooting

*   **I do not see notifications:** Check notification permissions in macOS Settings, confirm alerts are enabled in the app, and ensure they are not paused.
*   **I do not hear alert sounds:** Confirm sound is enabled for the alert level, check system volume, and ensure alerts are not paused.
*   **Cleanup shows no targets:** Ensure presets are selected and enabled, targets exist and are readable, and the folders are not already empty.
*   **Cleanup reclaimed less space:** Files may have changed, been locked, or deletions failed. Check the cleanup result for failure entries.
