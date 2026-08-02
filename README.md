# ⬡ GeoV Studio

**A real nonlinear video editor that runs in one HTML file — built for kids, proven in a classroom.**

🎬 **Live:** [sfdimarco.github.io/GeoV-Studio](https://sfdimarco.github.io/GeoV-Studio/) · works offline, no accounts, no installs, nothing to lose.

GeoV Studio is a VFX digital literacy suite for elementary students. Kids at a summer film camp chose it over Adobe, iMovie, Stop Motion Studio, and FlipaClip — *"it just feels a lot more fun to work with."*

## What kids can do

**🎞 Edit** — multi-layer timeline with free clip placement, trim, split, opacity, blend modes, chroma key with an eyedropper, per-clip audio with fades, and a master-bus limiter so nothing ever clips.

**🎨 Animate** — three studios in one app: a raster flipbook (real cel animation with holds, onion skin, pressure brushes), a vector studio (shapes + bezier-eased keyframes with auto-key, like early Flash), and a stop-motion downshooter that works with the iPad camera.

**✨ Code** — p5.js sketches are first-class clips. Kids write generative title cards and effects with a loop-guarded, friendly-error editor, and the frames render deterministically into their exports.

**🎙 Sound** — a slide-up sound deck with Boomwhacker-colored keys, foley pads, and mic takes that bounce into ordinary audio clips on the timeline.

**📦 Take it home** — projects pack into a single `.geos` bundle (a real ZIP with all footage inside) for Drive or AirDrop. Autosave + crash recovery mean a closed tab costs nothing.

## Why it's interesting technically

- **One file.** The entire NLE — compositor, three animation studios, audio mixer, exporter — is a single ~350 KB HTML file with two vendored libraries (Mediabunny, p5.js). No build step, no server, no dependencies to rot.
- **Real exports.** WebCodecs H.264/AAC encoding at 1080p30, with an automatic realtime-recording fallback for devices without a fast encoder. Audio mixes in overlapping OfflineAudioContext windows with limiter warm-up so seams are sample-exact.
- **Quadtree preview proxies.** Scrubbing uses GEO quadtree-compressed proxy frames so old Chromebooks and A12 iPads stay smooth; exports always decode the original footage.
- **Built for hostile hardware.** Element parking frees video decoders under memory pressure, bitmap LRU caches are sized per device class, and the whole app survives iPad Safari's layout, camera, and audio quirks — each one earned in the field.

## Classroom rules that shaped the design

1. **Nothing can get lost.** Trust bugs outrank features — autosave slots per open copy, NaN quarantine that self-heals corrupted projects, silent-export bugs treated as emergencies.
2. **The tool teaches.** Format chips explain codecs in kid language, the channel viewer and chroma key teach how digital images work, and code clips make effects programmable.
3. **Fun is a feature.** If it doesn't feel better than the app it replaces, kids won't choose it. They chose it.

---

Made by [Mook](https://sfdimarco.github.io) — artist, Unity developer, and STEAM teacher — with Claude as the engineering team.
