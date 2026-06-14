# Synthbit 🎵

A browser-based step sequencer and music composer built entirely with the **Web Audio API** — no dependencies, no installation, no server. Just open and play.

![Synthbit screenshot](screenshot.png)

---

## Features

- **Step sequencer** — 16, 32, 64, or 128 steps per pattern
- **41 scales and modes** from Western, Turkish/Arabic, Indian, East Asian, and other traditions
- **Long notes** — click and drag horizontally to extend a note across multiple steps
- **Multi-select** — Shift + drag to select a rectangular area; fill, delete, cut, copy, or paste
- **3 drum tracks** — Kick, Snare, Hi-hat with the same sequencer grid
- **4 waveforms** — Sawtooth (metal), Square (8-bit), Triangle, Sine
- **Score view** — visual staff output with synth notation and percussion symbols; print or export to PDF directly from the browser
- **5 save slots** — saves to browser localStorage; no account needed
- **Embeddable code export** — generates a self-contained HTML snippet with a Play button; paste into any webpage, no external files required
- **Turkish / English UI** — language toggle in the top bar

---

## Scales & Modes

| Region | Scales |
|---|---|
| Western | Major, Natural Minor, Harmonic Minor, Melodic Minor, Dorian, Phrygian, Lydian, Mixolydian, Locrian, Minor Pentatonic, Major Pentatonic, Blues, Whole Tone, Diminished, Enigmatic, Chromatic |
| Turkish / Arabic | Hicaz (Phrygian Dominant), Double Harmonic / Byzantine, Nihavend, Rast, Saba, Uşşak, Hicazkar |
| Indian | Bhairav, Yaman, Kafi, Bhairavi, Todi |
| East Asian | Chinese/Japanese Pentatonic, Yo, In, Hirojoshi, Iwato, Kumoi |
| Other | Algerian, Hungarian Minor, Romanian Minor, Neapolitan Minor, Persian, Arabian, Balinese Pelog |

---

## Usage

### Playing notes
- Click any cell in the **Synth** grid to toggle a note on/off
- Click and **drag right** on an empty cell to create a long (legato) note
- Multiple notes in the same column sound simultaneously (chords)

### Multi-select
- **Shift + drag** to select a rectangular region
- Use the action bar that appears: **Fill**, **Delete**, **Cut**, **Copy**, **Paste**

### Saving
- Use the **Save Slots** panel (5 slots) to save your work to the browser
- Saves all settings: notes, drums, tempo, scale, waveform, octave, step count

### Score / Print
- Click **♩ Score** to render a visual staff view
- Click **🖨 Print / PDF** to open the browser print dialog
- Select "Save as PDF" in the print dialog to export

### Embeddable export
- Click **⤓ Export Code** to generate a self-contained HTML snippet
- The snippet includes its own audio engine — paste it into any `<body>` tag
- No external files, libraries, or CDN links required

---

## How it works

Everything runs in the browser using the native [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API):

- **Synth voices** use `OscillatorNode` + `BiquadFilterNode` (lowpass) + `GainNode` with envelope shaping (attack/sustain/release)
- **Kick drum** — oscillator with rapid frequency drop (150 Hz → 50 Hz)
- **Snare** — noise buffer through a bandpass filter + short triangle oscillator
- **Hi-hat** — noise buffer through a highpass filter
- **Scheduling** — uses a lookahead timer pattern (`setInterval` + `AudioContext.currentTime`) for accurate, glitch-free timing
- **Score rendering** — HTML5 Canvas

---

## Browser support

Any modern browser with Web Audio API support:

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ |
| Firefox | ✅ |
| Safari (iOS & macOS) | ✅ |
| Opera | ✅ |

---

## Running locally

No build step needed. Just open the HTML file:

```bash
git clone https://github.com/yourusername/synthbit.git
cd synthbit
open index.html   # macOS
# or double-click index.html in your file manager
```

Or serve with any static server:

```bash
npx serve .
# then open http://localhost:3000
```

---

## Project structure

```
synthbit/
├── index.html      # entire app (single file, no dependencies)
└── README.md
```

---

## Roadmap / ideas

- [ ] MIDI export
- [ ] Microtonal / comma-adjusted tuning for Turkish makams
- [ ] Multiple synth channels (bass, lead, pad)
- [ ] Reverb / delay effects
- [ ] Pattern chaining (A→B→C)
- [ ] Mobile touch improvements

---

## License

MIT — do whatever you want with it.

---

*Built with the Web Audio API. No frameworks. No build tools. No nonsense.*
