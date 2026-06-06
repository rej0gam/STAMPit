# STAMPit

A standalone, offline-first transcription tool. No install, no dependencies, no subscription. Open `index.html` in Chrome or just click the host [https://rej0gam.github.io/STAMPit/](https://rej0gam.github.io/STAMPit/) and start transcribing.

Built out of frustration with InqScribe's sluggish editor and broken TAB handling.

---

## Features

### Core
- **Audio player** play/pause, rewind 3s, variable playback speed (0.5×–1.5×)
- **Timestamped editor** insert timestamps at cursor, click any timestamp to seek audio to that exact moment
- **Click to edit timestamps** click again to nudge the time, validates format on commit
- **Waveform scrubber** full-width waveform display, click or drag to seek
- **30fps / centisecond toggle** `.FF` format (00–29) matches InqScribe output, `.mm` (00–99) for centisecond workflows

### Transcription shortcuts
| Key | Action |
|-----|--------|
| `Tab` | Play / pause |
| `Ctrl+Space` | Insert timestamp at cursor |
| `Ctrl+−` | Rewind 3 seconds |
| `` `phrase` `` | Wrap as `[EN]phrase[/EN]` |
| `/l` | Insert `[laughter]` |
| `/c` | Insert `[cough]` |
| `/u` | Insert `[unintelligible]` |
| `/1` | Insert `[SPK1]` |
| `/2` | Insert `[SPK2]` |
| `Ctrl+H` | Find & replace |

### EN tag system
Type `` `phrase` `` (backtick open and close) to wrap English words or phrases in `[EN]phrase[/EN]` tags — designed for Filipino/English mixed-language transcription. Backspace immediately after closing tag reverts it for re-editing.

### Slash command palette
Type `/` to open a floating command palette showing all available annotations. Type the shortcut key to commit instantly, or navigate with arrow keys and Enter.

### Session management
- **Auto-save** saves your work 2 seconds after you stop typing
- **Session picker** when you reload an audio file, STAMPit finds previously saved sessions for that file and lets you restore or start fresh
- **Session rename** click any session label in the picker to rename it
- **Multiple sessions per file** up to 5 sessions per audio file, oldest dropped automatically
- **Connect folder (Chrome only)** uses the File System Access API to save sessions as `.json` files directly to a folder on your machine (e.g. `Documents/STAMPit/`). Falls back to browser localStorage on other browsers.

### Other
- **Find & replace** live highlighting, prev/next navigation, replace one or all
- **Export** downloads transcript as plain `.txt` with timestamps inline
- **Dark / light mode**
- **Unsaved changes warning** prompts before discarding work

---

## Timestamp Format

STAMPit uses `[HH:MM:SS.FF]` by default — 30fps frame timecode matching InqScribe's output format, where the last two digits range from `.00` to `.29`.

Toggle to `.mm` (centiseconds, `.00`–`.99`) in the sidebar if your workflow requires it.

### Format Converter

A companion converter tool is included (`converter.html`) for converting existing InqScribe transcripts from `.FF` frame timecode to `.mm` centiseconds. Load a `.txt` file, preview the converted output, download as `filename_converted.txt`.

---

## Browser Support

| Browser | Core | Waveform | Save to Disk |
|---------|------|----------|--------------|
| Chrome 111+ | ✅ | ✅ | ✅ |
| Edge 111+ | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ❌ (localStorage only) |
| Safari | ✅ | ✅ | ❌ (localStorage only) |

Chrome is recommended for the full experience including folder-based session saving.

---

## Usage

1. Open `index.html` in Chrome (or visit the hosted version)
2. Click **load audio** in the player bar to load an `.mp3`, `.wav`, `.aac`, or `.ogg` file
3. Click in the editor and start typing
4. Use `Tab` to pause/play, `Ctrl+Space` to stamp the current time
5. Click any blue timestamp to seek audio to that point

---

## Hosted

[https://rej0gam.github.io/STAMPit/](https://rej0gam.github.io/STAMPit/)

---

## Custom Tag Requests

Have a specific workflow that needs different tags — different languages,
custom annotations, speaker formats, or anything else? Open an issue or
reach out directly.

 [gammadrejey2018@gmail.com](mailto:gammadrejey2018@gmail.com)

---

## Support

If STAMPit saved you from InqScribe, consider buying me a coffee

[![Ko-fi](https://img.shields.io/badge/Ko--fi-support-ff5e5b?style=flat&logo=ko-fi)](https://ko-fi.com/gammadrejey2018gmailcom)

---

## License

MIT License — free to use, modify, and distribute.

---

*Built by Rej*
