# Animation-3d

**THE TEXT FROM TOMORROW** — a ~50 second low-poly 3D animated mystery short, built as a
single self-contained HTML file with [three.js](https://threejs.org). Vertical 9:16, sized for
YouTube Shorts / Reels.

## Run it

Open `index.html` in a modern browser, or serve the folder:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

Click the play button (it asks for fullscreen). The three.js module is loaded from
`cdn.jsdelivr.net`, so the first load needs an internet connection.

## What's in the file

| Section | Contents |
| --- | --- |
| 1 | WebAudio SFX engine — ambience, notification, knock, footsteps, stinger |
| 2 | Narration via `speechSynthesis` (male English voice preferred) |
| 3 | Script: 7 scenes, subtitle cues, per-scene narration text |
| 4–7 | Scene, lighting, the street, NPCs, Alex's house |
| 8 | Procedural human rig (hips → thighs → knees → feet) with expressions |
| 12 | Shot list / director — 33 shots, narration-gated scene cuts |
| 13–16 | Subtitles, playback control, layout, render loop |

## Narrated vs. silent

- If `speechSynthesis` is available, the narration drives the subtitle timing and the director
  holds the last shot of a scene until the voice finishes (capped at 2.4 s).
- If it isn't available, the short still plays end to end (~49 s): subtitles are timed against
  each scene's own shot length instead of a voice track.

## Recording for YouTube

Play it in fullscreen at 1080×1920 and screen-record (OBS: 1080×1920 canvas, 30 or 60 fps),
starting the capture after the intro fade so no UI chrome ends up in the take. The sound
button mutes both the SFX and the narration.
