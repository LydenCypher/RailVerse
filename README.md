# RailVerse: The Living Railway

RailVerse is an international 3D railway construction, driving, electrical engineering, signaling, timetable dispatching, passenger simulation, and world-building project.

## Repository Overview

This repository maintains three synchronized layers while preserving all existing website and release infrastructure:

1. **Interactive 3D WebGL Vertical Slice & Second Integrated Scenario (`src/simulation/`, `src/pages/PlayPage.tsx`, `src/components/RailVerseViewport3D.tsx`)**:
   - Playable directly in the browser at `/play` using Three.js WebGL and a deterministic 20 Hz SI-unit simulation loop.
   - Implements the **First Playable Vertical Slice (#33)** and **Second Integrated Playable Scenario (#34)**:
     - Two stations (`Helvetia Alpine Terminal` and `Lac-de-Glion Regional`) connected by a 1435 mm standard-gauge 15 kV AC 16.7 Hz electrified corridor plus a freight siding and functional switch (`node-jct-1`).
     - Interactive 3D spline track & station construction with live curve-radius, gradient, and gauge compatibility validation, plus Undo/Redo and Live Creation transactional safety interlocks.
     - Substation & section-level electrical network simulation with circuit breakers, isolators, overload faults, and regenerative braking energy recovery.
     - Interactive Train Cab (Throttle, Service/Emergency/Parking Brakes, Reverser, Pantograph, Main Circuit Breaker, Passenger Doors with traction interlock, Headlights, ATO Autopilot, Vigilance, Assisted Startup).
     - Block occupancy signaling, route reservations, switch locking, and automatic Level Crossings with animated barriers and road traffic.
     - Visual Timetable Editor with SVG Time-Distance Graph and automatic conflict detection.
     - Level A/B Passenger Simulation with boarding, alighting, capacity limits, and contextual NPC dialogue.
     - Dispatcher Radio & multi-channel chat, 16 Game Modes, Preset Workshop with schema validation, Customizable HUD Designer, Sanitized Local Bug Reporter, and Versioned Save/Load (`v1 -> v2` migration).
2. **Unreal Engine 5.4 C++ Scaffold & Independent Core (`RailVerse.uproject`, `Config/`, `Source/RailVerse/`, `Tests/RailVerseCoreTests.cpp`)**:
   - Modular C++ core header and test harness ready for Unreal Engine 5.4 compilation (`scripts/build-windows.ps1`).
3. **Standalone Rust Simulation Core (`rust-core/`)**:
   - Pure Rust implementation (`Cargo.toml`, `src/lib.rs`) of the deterministic railway network and SI train physics engine.

## Quick Start

```powershell
# Run automated unit & integration tests (Vitest)
npm.cmd run test

# Type-check and build production bundle
npm.cmd run build

# Start interactive development server
npm.cmd run dev
```
