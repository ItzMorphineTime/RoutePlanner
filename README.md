# Map Itinerary Planner

A lightweight, client-side web app for building day itineraries on an interactive map. Add stops, reorder them, visualize routes, estimate travel time, and export/share your plans as JSON or a link.

---

## Features

### Map-first planning
- **Interactive map (Leaflet + OpenStreetMap tiles)**
- **Right-click to add a stop** at any point on the map
- **Click a stop** to zoom/focus it on the map
- **Markers + popups** for quick stop identification
- **Auto-fit to stops** for a clean overview

### Stop management
- **Side panel stop list** with fast scanning and selection
- **Drag & drop reordering** (SortableJS)
- **Inline editing per stop**
  - Stop name
  - Start time / end time
  - Notes
- **Delete stop** controls
- **Undo / Redo**
  - Buttons in the UI
  - Keyboard shortcuts: `Ctrl/Cmd+Z`, `Ctrl/Cmd+Y` / `Shift+Ctrl/Cmd+Z`

### Routing & estimates
- **Route estimation modes**
  - Walking
  - Cycling
  - Driving
  - Public transport (Transit)
- **Public transport routing via TfL Journey Planner**
  - Select transit mode (e.g. **Tube**, **Bus**, **National Rail**, etc.)
  - Draws route geometry where available
  - Shows leg summaries (instructions) in Route Details
- **OSRM routing for walking/cycling/driving**
  - Distance + duration estimates
  - Route polyline rendering
- **Resilient fallback estimates**
  - If routing services are unavailable, uses approximate (Haversine-based) estimates
- **Per-stop route leg details**
  - Each stop displays the planned route to the next stop
  - Transit legs show step summaries (where provided)

### Import / Export / Sharing
- **Export itinerary to JSON** (copy + download)
- **Import itinerary from JSON**
  - Paste JSON directly
  - Load a `.json` file
  - Supports versioned schema (v2) with basic backward compatibility
- **Shareable link export**
  - Encodes the itinerary into the URL hash for easy sharing
  - Attempts compressed encoding when available, with a safe fallback
- **Local persistence**
  - Saves state to the browser (so your itinerary survives refresh)

### UX & quality-of-life
- **Auto-estimate toggle** (recompute routes after changes)
- **Route details dialog**
  - Total distance + time
  - Per-leg breakdown
  - Transit step summaries (when available)
- **Toast notifications** for feedback (imports, updates, errors, etc.)
- **Keyboard-friendly dialogs**
  - `Enter` to confirm add stop
  - `Esc` closes dialogs

### Usage
- Goto: https://itzmorphinetime.github.io/RoutePlanner/
- Right-click on the map to add a stop.
- Drag & drop stops in the left panel to reorder the itinerary.
- Edit each stop’s start/end times and notes.
- Choose a routing mode (Walking/Cycling/Driving/Public transport).
- Click Estimate (or enable Auto estimate) to compute travel time/distance.
- Use Export to copy/download JSON, or Share to copy a link.

###Tech Stack
- Leaflet for map rendering
- OpenStreetMap tiles
- SortableJS for drag & drop stop reordering
- OSRM (public demo server) for walking/cycling/driving routing
- TfL Journey Planner API for public transport routing
