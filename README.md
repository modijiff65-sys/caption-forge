# Caption Forge

A single-file web app for styling YouTube captions — built for text-style gaming videos (no voiceover needed).

Set the text, colour, outline, position and animation, watch the live preview, then export a `.ass` subtitle file that burns cleanly onto your video with `ffmpeg`.

## Features

- Live preview over a mock game screen
- Font size (as a % of frame height), text colour, outline colour and outline width
- Position: top / middle / bottom
- Animation: none / fade / pop
- Five presets: Classic Yellow, MrBeast, Neon Cyan, Fire Orange, Clean White
- Canvas presets: 1920×1080, 1280×720, 1080×1920 (Shorts), 1080×1080
- Multiple caption lines with start/end timings
- Export `.ass` (burn-in) or `.srt` (YouTube upload)

## Usage

Open `index.html` in any browser. Everything runs locally — no server, no tracking.

1. Pick a preset or dial in your own style.
2. Add your caption lines and their timings (seconds).
3. Click **Export .ass**.
4. Burn it onto your video:

```bash
ffmpeg -i input.mp4 -vf "ass=captions.ass" -c:v libx264 -crf 18 -preset veryfast -c:a copy output.mp4
```

## Why `.ass` and not just `.srt`

`.ass` (Advanced SubStation Alpha) supports colour, outline, shadow, positioning and animation per line — the bold-outline look that text-style gaming videos use. `.srt` carries only plain text, so it is offered for uploading as YouTube subtitles instead.

## Licence

MIT — do whatever you like with it.
