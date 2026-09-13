# Riff Lab

Hear a guitar riff, get the notes, tab, rhythm, and the key.

Riff Lab listens to you play (computer mic or an audio interface) and instantly writes down what you played as standard notation and guitar tablature, detects the scale/key, and teaches you one true thing about it. Save your ideas to a local library so you can pick them up later. A capture tool for songwriters who can play but do not read music.

Built as a hackathon prototype with Claude (Opus 4.8) in Claude Code.

## Features
- Real-time monophonic pitch detection (Web Audio) plus a built-in tuner
- Standard notation and a 6-line guitar tab (VexFlow), with rhythm and time signature
- Scale/key detection with a plain-English theory note
- Tuning-aware tab: Standard, E-flat, D (whole-step down), Drop D, Drop C-sharp, Drop C
- Tab / Notation / Both view toggle, each auto-sizing so nothing clips
- Save ideas to a local library (localStorage)
- Works with a plain computer mic (acoustic) or an audio interface like an Apollo Twin X (electric)

## Run it
The mic needs a secure context, so use localhost or HTTPS:

```bash
python3 -m http.server 8792
```

Then open http://localhost:8792 in Chrome, pick your input, and play a single-note riff.

## Tech
A single self-contained HTML file. Web Audio API for capture and pitch detection, VexFlow for notation and tab. No backend, no build step, runs entirely client-side. Polyphonic (full strummed chords) is intentionally out of scope for this prototype; it reads single-note lines.
