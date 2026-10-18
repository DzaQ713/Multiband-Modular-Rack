Freeware Windows x64 VST3: three dynamic multiband FX racks, a three-lane wavetable synth, modulation, randomizers, Master EQ/limiter and separate band outputs.
================================================

MULTIBAND MODULAR RACK — v1.3.4
-------------------------------

A C++/JUCE audio effect for processing, synthesis and sound design. Choose a source, split it into LOW/MID/HIGH and build an independent effect chain for each band.

Freeware binary distribution. Development sources remain private; a public download or repository page does not imply an open-source license. Use and redistribution follow the owner's published terms.

INPUT
-------------------------------
- AUDIO, SYNTHESIZER and GENERATOR are mutually exclusive; AUDIO is the default.
- Modular wavetable synth with an earlier Legacy engine for compatible older patches.
- White noise, pink noise and frequency-adjustable sine testing. The generator's post-output spectrum runs only while the generator is active and its analyzer panel is visible.
- Loading a saved generator state disarms the test source and selects AUDIO.

MODULAR SYNTH
-------------------------------
- Three independently scrolling, top-down wavetable lanes with CLASSIC/HARMONIC/FORMANT families, position scanning, warp and 1–8 unison voices per lane.
- Add, remove, enable and reorder Wave Shaper, Filter, Amp Envelope and Level/Pan cards. Card order changes DSP; each card type occurs once per lane.
- Six ADSR envelopes with curvature and NOTE/tempo-synced LOOP; loop rates from 2/1 to 1/64.
- Eight LFOs with basic and editable curves, four macros, four smooth random sources and MIDI modulation sources.
- Sixteen modulation routes with signed depth, drag-and-drop assignment and inline MOD editors. Clicking the same MOD again closes its editor without removing connections.
- POLY with 1–16 notes, MONO/LEGATO and 0–2000 ms glide for overlapping mono/legato notes.
- Constrained RANDOM, previous-patch UNDO RANDOM and confirmation-based CLEAR.
- Docked OUTPUT GUARD appears only in INPUT → SYNTHESIZER. It combines source-level protection and performance/shared filter controls; later rack processing can raise level again.

DYNAMIC FX RACKS
-------------------------------
- Adjustable linear-phase FIR crossover, per-band SOLO/MUTE and 1x/2x/4x/8x rack oversampling.
- Independent dynamic instances, repeated types and no fixed manual chain-length limit beyond system resources.
- 18 types: Clipper, Saturation, Distortion, Compression, Phaser, Chorus, Stereo Width, Limiter, Gate, Transient Shaper, Flanger, Stereo Delay, Reverb, Wah, Frequency Shifter, Ring Modulator, Comb / Resonator and Exciter.
- Compressor characters: Legacy, FET Fast, Opto Leveler, VCA Bus and single-band UP/DOWN, with model-specific controls and one INPUT/MIX/OUTPUT set.
- Individual POWER/INPUT/MIX/OUTPUT, input/output meters and double-click factory reset.
- RANDOM RACK: 3–7 distinct creative FX plus an additional limiter. Individual FX RANDOM retains INPUT/OUTPUT/POWER. CLEAR asks before emptying and muting a rack.
- MUTE fades a band out, suspends its FX/oversampling and restarts fresh histories on unmute. Delay/reverb tails are discarded. Crossover and latency alignment keep running; the parallel dry path still follows MASTER MIX.

HARDWARE-INSPIRED WORKSPACE
-------------------------------
- Compact three-column FX cards with metal panels, screws, recessed displays, I/O rocker switches and dice controls.
- Saturation model artwork; distinct compressor panels, knobs and measured gain displays.
- Individual synth module fronts, separate Master EQ/Limiter racks and a compact synth Guard.
- Shared enclosure rails/handles, warm lettering, neutral standard knobs and amber scrollbars.
- Effect-specific live meters/spectra and explanatory curve, timing and response previews. Tutorial descriptions identify the data shown.
- Translucent drag image, animated destination gap and edge autoscrolling for FX/synth reorder. Audio order commits on a valid drop; reordering stays within the current rack/lane.
- Proportional 1150 × 780 to 2300 × 1560 window resizing; no UI SIZE slider.
- English Tutorial Mode, enabled for new instances, with immediate hover explanations and readable wrapped text.

MASTER AND ROUTING
-------------------------------
Ten-point Master EQ, HP/LP and SOLO BAND; Master Limiter with INPUT, CEILING, RELEASE, LOOKAHEAD and post-ceiling GAIN COMPENSATION. Waveform is measured after compensation but before final MASTER OUTPUT. The final gain has a separate peak meter.

MASTER sends stereo to 1/2. ROUTING bypasses Master processing, silences 1/2 and sends LOW to 3/4, MID to 5/6 and HIGH to 7/8. Enable and connect extra buses in the host. MMR does not create DAW tracks or configure sends automatically.

PRESETS AND COMPATIBILITY
-------------------------------
- SAVE AS opens name entry; SAVE confirms overwriting the selected preset; DELETE confirms removal. Name collisions require confirmation. Deleting a preset does not change the current sound.
- Preset/project recall includes synth settings, modulation and dynamic FX types, counts, order, independent parameters and POWER.
- Preserved VST3 identity, 752 host parameters and preset schema 4. Additional dynamic instances retain state but do not automatically receive separate automation banks.
- Editor size and local tab/scroll state are restored on reopening. Full view-state persistence across DAW restarts is not claimed.

PLATFORM AND VALIDATION
-------------------------------
Windows 10/11 x64 VST3; C++/JUCE, Projucer, Visual Studio 2026. Route MIDI to the audio-effect plugin for synthesis. REAPER is the primary user-test host.

V1.3.4 Release x64 built successfully. Native checks cover preset UI actions, hardware font sizing, state, all FX and compressor models, MUTE, oversampling and reorder previews. Native checks do not replace listening, session recall and interactive testing in a DAW.

No macOS/Linux/AU/AAX release, exact hardware recreation, external wavetable import or Vital preset compatibility is advertised. Higher voices/unison/oversampling and longer chains use more resources. Output protection is sample-based and depends on its place in the chain; later gain can exceed earlier ceilings.

REPORTING ISSUES
-------------------------------
Include plugin version, Windows/DAW versions, input source and synth engine, sample rate, buffer size, polyphony/unison, oversampling, output mode, steps to reproduce and a preset or routing description where relevant.
