# NEON DRIFT: Cyber Runner

**A standalone, zero-asset-dependency 3D synthwave endless runner built for the browser.**

NEON DRIFT uses Babylon.js, the Web Audio API, and Firebase Firestore to deliver solo, local, and real-time multiplayer racing experiences.

## Features

### Three Game Modes

- **Online Multiplayer Arena** — Create or join a live 4-letter room with real-time rival ship telemetry, shield synchronization, and shared deterministic obstacle generation.
- **2P Local Duel** — Race head-to-head on one screen with dynamic dual-pilot camera tracking.
- **Solo Run** — Chase a high score with persistent `localStorage` leaderboard tracking.

### Built-In Systems

- **Zero external 3D assets** — Hovercraft meshes, highway textures, cityscapes, lighting, and particle trails are procedurally generated.
- **Procedural synth soundtrack** — A real-time Web Audio arpeggiator provides music and dynamic SFX for jumps, orb pickups, shield activation, and crashes.
- **Deterministic courses** — A Mulberry32 PRNG gives every player in an online room the same sequence of barriers, laser hurdles, orbs, and shields.
- **Orbit camera** — Press `C` or use the HUD button to inspect the ships and environment in 360 degrees.

## Controls

| Action | Solo / Online | 2P Duel — P1 (Cyan) | 2P Duel — P2 (Crimson) |
| --- | --- | --- | --- |
| Steer left / right | `A` / `D`, arrow keys, or drag | `A` / `D` | Left / Right arrows |
| Jump / thruster | `W`, `Up`, `Space`, or tap | `W` or `Space` | `Up` |
| Orbit camera | `C` or HUD button | `C` or HUD button | `C` or HUD button |
| Toggle audio | `M` or HUD button | `M` or HUD button | `M` or HUD button |

## Architecture

- **Rendering:** Babylon.js with WebGL2/WebGL1 fallback, `GlowLayer`, `DynamicTexture`, and `ParticleSystem`
- **Multiplayer:** Firebase Firestore real-time room state and position synchronization
- **Audio:** Native Web Audio API oscillators and gain envelopes
- **Distribution:** Single-file HTML5 application with no build step or bundler

## Quick Start

Open `index.html` in a modern desktop or mobile browser:

- Chrome
- Edge
- Safari
- Firefox

No build or install step is required for local testing.

## Multiplayer Setup

1. Enable Firestore in Firebase test or production mode.
2. Allow read/write access for the `neon_drift_rooms` collection.
3. Replace the Firebase web app configuration in `index.html` with credentials for your own project.

For production hosting, review Firebase authentication, Firestore rules, and usage limits before launching.

## Customization

All primary game settings are in the `CONFIG` object inside `index.html`.

- Change visual colors and neon tones in `CONFIG.COLORS`.
- Adjust `BASE_SPEED`, `MAX_SPEED`, and `SPEED_ACCEL` to tune difficulty.
- Change `SPAWN_Z`, `DESPAWN_Z`, and obstacle timers to modify course density and pacing.

## Commercial Readiness

- 100% procedural art and original code
- No third-party 3D models or copyrighted audio tracks
- Suitable for custom portal wrappers and browser-game platforms
