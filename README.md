MULTIBAND MODULAR RACK
====================================
By DzaQ713

Free Windows x64 VST3 combining three-band effects, a modular wavetable synthesizer, a test generator and master processing. Built in C++ with JUCE. This repository accompanies binary releases, documentation and issue reporting; development sources remain private. Freeware does not imply an open-source licence.

INPUT AND SIGNAL FLOW
------------------------------------
Choose one source: AUDIO (default DAW input), SYNTHESIZER (MIDI instrument) or GENERATOR (white noise, pink noise or adjustable sine). The source feeds a complementary linear-phase crossover and independent LOW, MID and HIGH racks. Rack oversampling offers 1x/2x/4x/8x.

The generator's post-Master-Output spectrum runs only when GENERATOR and its analyzer panel are active. Loading saved generator settings disarms the test source and returns to AUDIO. The synth Output Guard appears only in INPUT > SYNTHESIZER and protects the synth before downstream effects.

MODULAR WAVETABLE SYNTH
------------------------------------
- Three independently scrolling top-down wavetable lanes with docked waveform headers.
- Ten factory families / 40 frames, Position scanning, tuning, phase, Warp/Amount and 1-8 unison voices per lane with detune/spread.
- Reorderable Wave Shaper, Filter, dedicated Amp Envelope and Level/Pan audio modules. Each audio-module type occurs once per lane.
- POLY up to 16 notes, MONO/LEGATO, glide and MIDI sustain. Route MIDI to this audio-effect plugin to play it. The Legacy engine remains available.
- Each lane has its own AMP envelope with ADSR, Peak, separate Attack/Decay/Release curves and looping.
- Parameter-local MODS racks contain independent LFO, Envelope, Random, Macro, Velocity, Mod Wheel, Aftertouch and Key Track sources, edited directly at their destination.
- Scale, Offset, Curve, Slew and Quantize transformations shape modulation signals. Reordering transformations changes their processing order.
- Eligible modulator controls can themselves be modulated. Dependency validation rejects cycles; modulation is evaluated with per-voice separation where required.
- LFO/ENV editors support curve shaping, draggable envelope junctions and LFO point tangent/smoothness controls. Relevant editors provide history, randomization and Apply/Cancel audition.
- Tempo timing includes STRAIGHT, TRIPLET and DOTTED choices. Envelopes support NOTE or repeating LOOP; LFOs offer free/synced timing and retriggering.
- Clickable wavetable FX MAP groups modulation by destination and opens the corresponding editor, including nested modulation controls.
- Cyan knob markers show effective running DSP values and the spread between voices. Grey base and blue predicted waveform curves remain independent previews, not an audio oscilloscope.
- Synth RANDOM covers local sources, shapes, rhythms, curves and nested modulation while retaining an audible foundation. UNDO restores the previous patch; CLEAR asks for confirmation.

Local MODS racks support multiple sources and nested modulation. Practical complexity depends on system resources; generated patches use bounded sizes.

CUSTOM WAVE EDITING
Click a waveform to edit a four-frame CUSTOM bank. Select a base wave, including FLAT, and shape connected periodic segments with point selection, Amplitude, Q and Left/Right Curve. Base Phase and Points Phase can move independently or together through LINK. Point removal, zoom, history and randomization are available.

Draft audition follows the synth's modulation/Position path. Accept commits; Cancel restores the committed bank. Only committed geometry is saved. Older wave geometry is retained for compatibility. External wavetable-file import and Vital preset compatibility are not included.

23 FX FAMILIES / 148 MODELS
------------------------------------
Clipper; Saturation; Distortion; Compression; Phaser; Chorus; Stereo Width; Limiter; Gate; Transient Shaper; Flanger; Stereo Delay; Reverb; Wah; Frequency Shifter; Ring Modulator; Comb / Resonator; Exciter; Glitch / Stutter; Chop / Reverse; Tape / Vinyl Warp; Front / Back; Pitch Shifter.

Each family starts with MMR (default) and SIMPLE, followed by hardware-inspired models: 23 MMR, 23 SIMPLE and 102 other profiles. MMR uses its own expanded engine; SIMPLE exposes essential controls. Individual models retain their own settings, ranges and defaults. These are original behavioural interpretations, not certified component-exact hardware emulations.

Examples include Tube/Tape/Germanium saturation; FET/Opto/VCA/UP-DOWN/Vari-Mu compression; Fuzz/Rectifier/Sample Crush distortion; Barberpole/Vowel phasing; Ensemble/Dual/Vibrato chorus; Haas/Micro Detune/Mono Bass width; Room/Hall/Plate/Spring/Dual Space reverb; modal resonance; rhythmic capture/reverse; and tape/vinyl motion.

MMR Saturation and Distortion include EDIT CURVE: an amplitude transfer function, distinct from the synth's periodic wavetable. Add points, shape curvature and audition before Apply. Saturation keeps a monotonic curve; Distortion permits folding and rectification. Editable starting presets, Reset and local Undo/Redo are available. Each instance saves its committed curve; Cancel restores it.

Pitch Shifter offers stepped -12 to +12 semitones and adjacent CENTS fine tuning. MMR has manual Formant and two-voice creative controls. Other models use opposite-direction automatic formant compensation at half the effective pitch. Processing adds latency and can require substantial CPU, especially with high oversampling and small buffers.

SERIAL AND PATCH ROUTING
------------------------------------
Each band independently selects its mode:

SERIAL ROUTING processes effects in rack order. PARALLEL is inactive and ignored by DSP, including stored values and host automation. No cables are shown.

PATCH ROUTING uses explicit stereo connections. Patch directly on the front cards or open the rear-panel FX MAP; both edit the same graph and effect instances.

- Connect BAND DI to DI IN, and effect outputs to FX IN or RACK OUTPUT. Several sources may feed an input; relative weights are normalized.
- Feedback loops, including zero-weight loops, are rejected. Direct clean DI-to-output patching is not allowed. Empty/all-muted racks retain bypass; disconnected active patches remain silent.
- With both input groups connected, PARALLEL blends clean band DI and processed sources. Connecting the missing second group starts at 50/50; adding a source to an existing group retains the current balance.
- With only DI or FX sources, PARALLEL is inactive. MIX separately blends each effect's input with its processed sound.
- Drag existing cables to rewire them, or drop them on empty canvas background to disconnect. Click inputs or right-click cables to inspect sources and weights. Invalid drops preserve the existing connection.
- Blue cables carry BAND DI; each effect has its own output-cable colour. Hover identifies the source and destination by effect/model names.
- Green targets accept a connection, red indicates a cycle, grey indicates an incompatible or existing connection.
- Routing Undo/Redo restores wiring, arrangement and structural changes; automatic 50/50 changes are included with their cable operation.

In PATCH, dragging a card changes only its visual position; its cables stay attached. SERIAL dragging changes audio order. Wiring can be edited directly on effect cards or through FX MAP, with BAND DI and RACK OUTPUT accessible while scrolling.

Trying PARALLEL in SERIAL asks whether to switch to PATCH and connect DI. Confirmation copies the serial chain, replaces saved PATCH wiring and starts at 50/50 where a second group is added. The first DI-only effect remains DI-only. Saved PATCH wiring can also be restored through the mode selector.

RACK WORKFLOW
------------------------------------
- Dynamic chains allow repeated effect types with independent settings and no fixed manual chain-length cap.
- Click + to choose a model submenu, or click the family name to add MMR directly.
- FX Solo auditions that effect from BAND DI. Mute/bypass overrides Solo and collapses the card while keeping its name and routing sockets. Band Solo/Mute suppresses the appropriate racks.
- Drag unused card space to reorder with a translucent preview and insertion gap. Click without dragging to open the same instance in a larger, modeless window. Controls and screens retain their own gestures.
- RANDOM RACK selects 3-7 distinct families from Wah, Saturation, Distortion, Exciter, Comb/Resonator, Phaser, Flanger, Chorus, Stereo Delay and Reverb, orders them logically and adds a protective final limiter. Models span MMR, SIMPLE and hardware-inspired profiles.
- RANDOM FX retains its instance and cables. MIX randomizes within 50-100%; manual adjustment remains 0-100%, and new FX start fully wet. INPUT/OUTPUT are not randomized.
- PARALLEL randomizes only in PATCH: 0/50/100% with 40/20/40% probability. The final guard remains fixed.
- RKR is a diagnostic knob-sweep mode with independent phases and unique 2-10 second periods. PARALLEL, INPUT, MIX, OUTPUT and SYNC are excluded. Stop retains current values; state loading leaves RKR off.
- CLEAR asks before removing a rack. PATCH replacement/removal actions have routing-aware confirmations.

MASTER PROCESSING AND BAND OUTPUTS
------------------------------------
- Ten-point Master Parametric EQ with Band/Low Shelf/High Shelf shapes, graph selection, selectable muted points and Solo Band audition.
- Frequency, Q, base Gain and independent Mid/Side Boost (-18 to +18 dB each) per point. Effective gain is base Gain plus the corresponding boost. HP/LP have stepped OFF/12/24/48 dB/oct controls.
- Dynamic EQ per point: Threshold -36 to 0 dBFS, Ratio 0.5:1 to 12:1, Attack 0.10-500 ms and Release 10-3000 ms. Defaults: OFF, 0 dBFS, 1:1, 30 ms, 100 ms. Ratios below 1 expand above threshold; ratios above 1 compress.
- Master Limiter: Input gain, Ceiling, Release, Lookahead and post-ceiling Gain Compensation. Its Waveform/compensated ceiling reference is before final MASTER OUTPUT; that final gain has a peak meter.
- EQ/Limiter OFF bypasses the respective processing, stops its analysis and shows a dimmed grayscale section without plots; alignment delays are retained.
- MASTER sends the stereo master to 1/2. ROUTING bypasses master processing, silences 1/2 and sends LOW/MID/HIGH to 3/4, 5/6, 7/8. Enable and connect those buses in the DAW; the plugin does not create tracks or sends.

INTERFACE, PRESETS AND REQUIREMENTS
------------------------------------
Hardware-inspired controls and model-specific visual identities accompany effect-specific displays: analogue meters, stereo modulation, echoes, reverb tails and reference WAVE/HARMONICS where relevant. All artwork is included in the plugin.

English Tutorial Mode explains controls as you explore. Resizable windows, UI scaling and independently scrolling racks help adapt the workspace to your screen and project.

SAVE AS asks for a name; SAVE/DELETE ask for confirmation. Presets/projects retain dynamic instances, model banks, order, mute/solo, committed custom waves/transfer curves, local modulation and rack wiring. Extra dynamic instances/modulators do not automatically gain unlimited individual host-automation slots.

Windows 10/11 x64 with a VST3-compatible DAW. Separate MSVCP140/VCRUNTIME140 runtime DLLs are not required. No macOS/Linux/AU/AAX release is supplied. Host compatibility is not exhaustive; the reported Cubase 12 loading issue remains unverified.

CPU/memory depend on models, buffers, voices and oversampling. Protection applies where it sits in the chain; later gain and positive post-ceiling compensation can raise peaks again. Declared latency is compensated; intentional filter/modulation phase response remains. Older engines, normalized automation mappings and AUTO endpoint-based routing may need review when moving older projects to the current explicit PATCH model.

For bug reports, include MMR/DAW/Windows versions, sample rate, buffer size, oversampling, input/routing mode, reproduction steps and a relevant preset.

Free download: https://dzaq713.itch.io/multiband-modular-rack
