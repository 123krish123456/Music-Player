# Cassette Music Player

A Windows desktop music player built around the animated cassette tape UI.

## Setup

1. Make sure Python 3.8+ is installed (https://python.org)
2. Install dependencies (one-time):
   ```
   pip install pygame mutagen pywebview
   ```
3. Run the player:
   - **Double-click** `launch_player.bat`  — installs deps and launches
   - **Or directly:** `pythonw cassette_music_player.pyw`

## Features

### Playback
- Play / Pause / Previous / Next
- Animated cassette reels, tape, and EQ bars sync to playback state
- Progress bar: click anywhere to seek
- Volume slider (0–100%)

### Folder & Playlist
- Click **OPEN FOLDER** (or the 📁 button) to pick a music folder
- All supported audio files load automatically as a playlist
- Supported formats: `.mp3` `.flac` `.ogg` `.wav` `.m4a` `.aac` `.mp4`
- Track metadata (title, artist, duration) read from file tags
- **Double-click** any playlist track to play it immediately

### Queue
- Opening a folder auto-fills the queue with all tracks in order
- From the **Playlist** tab, hover a track to reveal two buttons:
  - **▷** — Insert track right after the currently playing song ("Play next")
  - **+** — Append track to the end of the queue
- Switch to the **Queue** tab to see and manage the playback order:
  - **Drag rows** up/down to reorder
  - **✕** button to remove a track from the queue
  - **SHUFFLE** — randomises all tracks *after* the current one
  - **CLEAR** — empties the queue and stops playback
- **Double-click** a queue entry to jump to it immediately

## Notes
- The queue position (currently playing slot) is always tracked correctly
  even after drag-reorder operations.
- Seeking uses pygame's `set_pos` — works best with MP3/OGG.
  WAV files may not seek accurately.
