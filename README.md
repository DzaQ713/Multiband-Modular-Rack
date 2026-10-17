Freeware Windows x64 VST3: three dynamic multiband FX racks, a three-lane wavetable synth, modulation, randomizers, Master EQ/limiter and separate band outputs.
================================================

MULTIBAND MODULAR RACK - v1.2.10

A C++/JUCE audio effect combining three input sources with independently configurable LOW, MID and HIGH processing racks.

This project is intended for freeware binary distribution. Development sources remain private. A public release/download page does not imply an open-source license or grant redistribution rights beyond the owner's published terms.

INPUT
- AUDIO, SYNTHESIZER or GENERATOR, mutually exclusive; AUDIO is the default.
- Built-in Modular wavetable synthesizer plus the earlier Legacy engine for older patches.
- White noise, pink noise and sine test source with a dedicated processed-output spectrum display, active only for the generator.

MODULAR SYNTH
- Three independently scrolling top-down wavetable lanes.
- Built-in CLASSIC/HARMONIC/FORMANT tables, position scanning, tuning, warp and 1-8 unison voices per lane.
- Add/remove/power/reorder Wave Shaper, Filter, Amp Envelope and Level/Pan cards; their order changes DSP.
- Six ADSR envelopes with curvature, NOTE/tempo-synced LOOP and rates 2/1-1/64.
- Eight LFOs, editable eight-point LFO curves, four macros, smooth random sources and MIDI modulation.
- Sixteen modulation routes, drag-and-drop assignment and inline MOD editors.
- POLY 1-16 notes, MONO/LEGATO, last-note priority and 0-2000 ms GLIDE for overlapping mono/legato notes.
- Constrained RANDOM, snapshot UNDO RANDOM and confirmation-based CLEAR.
- Docked OUTPUT GUARD with synth level, sub, velocity, shared filter and performance controls; source overload/reduction indication.

FX AND MASTER
- Adjustable linear-phase FIR crossover with LOW/MID/HIGH SOLO and MUTE.
- Dynamic FX chains with independent instances, repeated types and drag-and-drop ordering.
- 18 types: Clipper, Saturation, Distortion, Compression, Phaser, Chorus, Stereo Width, Limiter, Gate, Transient Shaper, Flanger, Stereo Delay, Reverb, Wah, Frequency Shifter, Ring Modulator, Comb / Resonator and Exciter.
- Legacy, FET Fast, Opto Leveler, VCA Bus and UP/DOWN compressor characters.
- Per-effect POWER/INPUT/MIX/OUTPUT; rack oversampling 1x/2x/4x/8x.
- RANDOM RACK: 3-7 distinct creative FX plus an additional limiter. Per-effect RANDOM retains INPUT/OUTPUT/POWER. Rack CLEAR asks before emptying and muting the selected band.
- Ten-point Master EQ, HP/LP, SOLO BAND and Master Limiter with input gain and post-ceiling compensation.
- Limiter Waveform before final MASTER OUTPUT; final output meter.

ROUTING
MASTER outputs stereo on 1/2. ROUTING bypasses Master processing, silences 1/2 and sends LOW to 3/4, MID to 5/6 and HIGH to 7/8. Enable and route the additional buses in the host; MMR does not create DAW tracks or configure sends automatically.

INTERFACE AND STATE
- INPUT / FX RACKS / MASTER OUTPUT tabs.
- Compact 1150 - 780 reference layout with proportional window resizing up to 2300 - 1560; no UI SIZE slider.
- Docked input spectrum (20 Hz-22 kHz) and synth Guard, illuminated state buttons and English Tutorial Mode.
- Preset/project recall for synth settings and dynamic FX chains.
- Editor size/tab/scroll restoration on reopening; full view-state persistence across DAW restarts is not claimed.
- Earlier host parameter identities are preserved. Additional dynamic FX instances retain state but do not automatically receive separate host-automation banks.
- Loading a saved generator state disarms the test source and selects AUDIO.

PLATFORM AND LIMITS
Windows 10/11 x64, VST3; JUCE/Projucer, Visual Studio 2026. REAPER is the primary user-test host. MMR remains an audio effect: route MIDI to it for synthesis. No macOS/Linux/AU/AAX release or Vital preset/wavetable-import compatibility is claimed. Character processors are independent implementations, not exact hardware recreations.

The synth Guard is before the racks. Subsequent FX/gain/summing can raise output level. Higher voices/unison/oversampling increase CPU use, and the plugin reports latency. Native checks do not replace listening and session tests in a host.

REPORTING ISSUES
Include plugin version, Windows and DAW versions, source/engine, sample rate, buffer size, polyphony/unison, oversampling, output mode, steps to reproduce and the relevant preset or routing description.
