# 🎹 Synthbit

**A browser-based step sequencer and music composer built entirely with the Web Audio API — no dependencies, no build tools, just one HTML file.**

> Available in English and Turkish · İngilizce ve Türkçe arayüz desteği

---

## ✨ Features

- **Step sequencer** with 16, 32, 64 or 128 steps
- **Synth track** with 4 waveforms: sawtooth, square, triangle, sine
- **Drum track** with kick, snare and hi-hat (synthesized, no samples)
- **41 scales and modes** from world music traditions:
  - Western: Major, Minor, Harmonic Minor, Melodic Minor, all 7 modes, Blues, Whole Tone, Diminished, Enigmatic, Chromatic
  - Turkish / Arab: Hicaz, Double Harmonic / Byzantine, Nahawand, Rast, Saba, Uşşak, Hicazkar
  - Indian: Bhairav, Yaman, Kafi, Bhairavi, Todi
  - East Asian: Chinese/Japanese Pentatonic, Yo, In, Hirojoshi, Iwato, Kumoi
  - African / Other: Algerian, Hungarian Minor, Romanian Minor, Neapolitan Minor, Persian, Arabian, Balinese Pelog
- **1–3 octave range** per session
- **Long notes** — drag right across cells on the same row to create sustained notes
- **Multi-select** — Shift + drag to select a rectangle of cells, then fill, delete, cut, copy or paste
- **5 save slots** stored in the browser's localStorage (no server needed)
- **Score view** — visual staff notation with synth notes and percussion symbols, with Print / Save as PDF support
- **Embeddable code export** — generates a self-contained HTML snippet you can drop into any webpage
- **Bilingual UI** — English (default) and Turkish, switchable live with the 🌐 language selector

---

## 🚀 Usage

### Option A — Open directly in a browser

1. Download `synthbit.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Start composing

No installation, no server, no internet connection required after download.

### Option B — Host on GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages** and set the source to the `main` branch, root folder
3. Your Synthbit instance will be live at `https://<your-username>.github.io/<repo-name>/synthbit.html`

---

## 🎛️ How to use

| Action | How |
|---|---|
| Place a note | Click an empty cell |
| Remove a note | Click an active cell |
| Long / sustained note | Click and drag right across cells on the same row |
| Multi-select | Hold **Shift**, then click and drag |
| Cut / Copy / Paste | Select cells → use the toolbar that appears |
| Save your work | Click **Save here** in any of the 5 slots below the sequencer |
| Load a save | Click **Load** next to a saved slot |
| View score | Click **♩ Score** to open the staff notation view |
| Print / PDF | Open the score, then click **🖨 Print / PDF** |
| Export for web | Click **⤓ Export Code** → copy or download the HTML snippet |
| Switch language | Click **🌐 EN ▾** in the top-right corner of the control bar |

---

## 📄 Embeddable Export

The **Export Code** feature generates a standalone HTML snippet that encodes your entire composition — notes, rhythm, tempo, waveform — as inline data. Paste it anywhere inside a `<body>` tag:

```html
<!-- Paste inside your blog post, portfolio page, etc. -->
<div id="sb_abc12">
  <button id="sb_abc12b">▶ Play</button>
  ...
</div>
<script>
  (function(){ var D = { /* encoded composition data */ }; ... })();
</script>
```

The player renders a styled Play/Stop button. No CDN, no external scripts — fully self-contained.

---

## 🌍 Scale Reference

| Scale | Origin | Character |
|---|---|---|
| Hicaz (Phrygian Dom.) | Turkish / Arab | Dramatic, Middle Eastern |
| Double Harmonic / Byzantine | Turkish / Greek | Very exotic, two augmented seconds |
| Bhairav | Indian (morning raga) | Serene, devotional |
| Hirojoshi | Japanese | Dark, meditative |
| Enigmatic | Italian (Verdi) | Highly unusual, chromatic |
| Diminished | Western (symmetric) | Tense, widely used in metal |

---

## 🔧 Technical Notes

- Built with the **Web Audio API** — `OscillatorNode`, `GainNode`, `BiquadFilterNode`, `DynamicsCompressorNode`
- Drum sounds are fully synthesized: kick = pitched oscillator with frequency drop, snare = bandpass-filtered white noise, hi-hat = highpass-filtered white noise
- Uses a **lookahead clock** scheduler to prevent audio glitches under heavy CPU load
- Save slots use `localStorage` — persists across sessions on the same device
- Score view renders to HTML `<canvas>` and uses the browser's native print API for PDF export
- Zero external dependencies

---

## 📜 License

MIT — free to use, modify and distribute.

---

## 🤝 Contributing

Pull requests are welcome. Some ideas for future features:

- MIDI export
- Microtonal / comma-based tuning (for authentic maqam intonation)
- Additional synth voices (FM, AM)
- Pattern chaining / song mode
- More percussion sounds

---

*Made with the Web Audio API. No dependencies were harmed in the making of this project.*
