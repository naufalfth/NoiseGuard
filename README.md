# NoiseGuard

**Know when the noise around you is safe — or time to move away.**

Noise pollution is an everyday health problem: loud motorcycle exhausts, construction sites, traffic. NoiseGuard listens through your device microphone, measures the sound level in decibels, and tells you in plain language whether it is safe to stay or better to move away.

## What it does

- Live dB meter from your device microphone (Web Audio API, no audio leaves your device)
- Instant verdict: Safe / Fairly Noisy / Noisy / Dangerous, with exposure guidance
- 90-second history graph and session statistics (average Leq, peak, duration)
- Event log for moments above 85 dB
- Final environment assessment, from "Safe to stay" to "Dangerous, better to move away"
- Sound classification with Google Gemini: record a 5-second clip and Gemini identifies the sound, its risk level, and what to do (in Indonesian)
- Demo simulations (Quiet room, Highway, Loud exhaust, Construction) for presenting without a live microphone
- Works fully offline as a single HTML file. No server, no database, no install.

## How it works

- The microphone signal is measured in the browser and converted to an estimated dB level. A calibration slider is included.
- Verdict bands follow NIOSH exposure guidance and Indonesia's Kepmen LH No. 48/1996 noise quality standards.
- Sound classification uses the Gemini API (newest available Flash model, auto-selected): a short audio clip is sent directly from your browser to Google, and the answer comes back in Indonesian.

## Honesty note

A phone or laptop microphone is an estimate, not a certified sound level meter. NoiseGuard is an awareness tool, not a replacement for professional measurement.

## Run it

1. Open `index.html` in Google Chrome.
2. Click "Mulai Mengukur" and allow microphone access.
3. (Optional) Paste a free Gemini API key from Google AI Studio into the "Klasifikasi Suara — Gemini" card to enable sound classification. The key lives only in the page's memory while it is open and is never saved to the file.
4. Make noise, or pick a simulation, and watch the verdict change.

## Tech

- Single-file HTML, CSS and JavaScript. No build step, no dependencies.
- Web Audio API for live measurement.
- Gemini API (newest available Flash model, auto-selected) for audio classification.

## Built for

Google Cloud Gen AI Academy APAC Edition, "Meet the Builders".

## License

MIT. See `LICENSE`.
