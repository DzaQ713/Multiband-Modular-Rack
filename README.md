SHORT DESCRIPTION
=====================================
Free Windows x64 VST3: three-band modular FX, a wavetable synth with custom wave editing, 23 effect families, creative randomizers and separate band outputs.

MULTIBAND MODULAR RACK — v1.4.10
By DzaQ713

A C++/JUCE audio effect, instrument and sound-design workspace. Choose DAW audio, the MIDI synthesizer or a test generator; split the source into LOW/MID/HIGH and build an independent processing chain for each band.

This page accompanies the freeware binary releases, documentation and issue reporting. Development sources remain private. Freeware does not grant an open-source licence; use and redistribution follow the owner's published terms.

INPUT
------------------------------------
- Mutually exclusive AUDIO, SYNTHESIZER and GENERATOR sources; AUDIO is the default.
- White noise, pink noise and frequency-adjustable sine testing.
- The generator's dedicated post-Master-Output spectrum runs only while GENERATOR and its analyzer panel are active. Loading a saved generator state disarms the test source and returns to AUDIO.

MODULAR WAVETABLE SYNTH
- Three top-down lanes with docked waveform headers and independent scrolling.
- Ten factory families / 40 frames: CLASSIC, HARMONIC, FORMANT, PULSE, ODD ORGAN, EVEN GLOW, HOLLOW REED, METALLIC CLUSTER, SOFT FOLD and DIGITAL STEPS.
- POSITION scanning, tuning, phase, Warp/Amount and 1-8 unison voices per lane with detune/spread.
- Add, remove, enable and reorder Wave Shaper, Filter, Amp Envelope and Level/Pan cards. Each audio-card type occurs once per lane; order changes processing.
- Six ADSR envelopes with curvature and NOTE/tempo-synced LOOP; eight LFOs including drawn curves; four macros, four smooth random sources and 16 signed-depth modulation connections.
- POLY up to 16 notes, MONO/LEGATO and glide. Route MIDI to this audio-effect plugin to play the instrument.
- Inline MOD editors, constrained RANDOM, previous-patch UNDO and confirmation-based CLEAR.
- Grey static and blue predicted modulation references work without incoming MIDI/audio. NOTE, LOOP and FREE use their respective reference clocks.
- Docked OUTPUT GUARD appears only in INPUT > SYNTHESIZER. It protects the source before FX racks; later processing can raise level again.
- Earlier patches retain the Legacy engine and its original bank selectors.

CUSTOM WAVE EDITOR
Click a modular waveform to edit a four-frame CUSTOM bank. Use up to ten points per frame, POINT selection, AMPLITUDE, Q, LEFT/RIGHT CURVE and local segment shaping. BASE PHASE and POINTS PHASE can move separately or together through LINK. Zoom, point removal, local Undo/Redo and RANDOM are available.

Draft audition uses the actual synth modulation and Position path. Accept commits; Cancel restores. Unaccepted drafts are excluded from saved host state. CUSTOM banks and geometry are saved with presets/projects. External wavetable-file import is not included.

23 EFFECT FAMILIES
------------------------------------
Clipper; Saturation; Distortion; Compression; Phaser; Chorus; Stereo Width; Limiter; Gate; Transient Shaper; Flanger; Stereo Delay; Reverb; Wah; Frequency Shifter; Ring Modulator; Comb / Resonator; Exciter; Glitch / Stutter; Chop / Reverse; Tape / Vinyl Warp; Front / Back; Pitch Shifter.

Examples of model/type choices:
- Saturation: Tube, Tape, Transistor, Transformer, Console, Worn Tape, Germanium, CUSTOM.
- Compression: Legacy, FET Fast, Opto Leveler, VCA Bus, UP/DOWN, Vari-Mu, Diode Bridge, Clean RMS.
- Distortion: Bit Crush, Soft Clip, Hard Clip, Foldback, Fuzz, Rectifier, Sample Crush, CUSTOM.
- Modulation: Barberpole/Vowel Phaser, Ensemble/Dual/Vibrato Chorus, Through-Zero/Tape Flanger and alternative Wah shapes.
- Stereo Width: Haas, Micro Detune and Mono Bass alongside original M/S width.
- Dynamics: Adaptive Release/Lookahead Limiter, Expander/Ducker, Adaptive/Dual-Time Transient Shaper.
- Digital/Tape/BBD delay with Stereo/Ping-Pong/Multitap routing; Room/Hall/Plate/Spring reverbs.
- Additional Clipper, Shifter, Ring, Comb/Resonator and Exciter characters.

CUSTOM SATURATION AND DISTORTION
Use CUSTOM and the separate EDIT button to draw an input-to-output transfer curve. Add up to ten interior points plus two end points, move them or adjust their curvature. Saturation preserves a monotonic response; Distortion permits folding and rectification. This editor shapes audio amplitude, unlike the synth editor's periodic wavetable.

CURVE PRESET provides editable starting points:
- Saturation: NEUTRAL, TUBE, TAPE, CONSOLE, GERMANIUM.
- Distortion: NEUTRAL, SOFT DIODE, HARD DIODE, ASYMMETRIC FUZZ, RECTIFIER, FOLDBACK.

Audition changes before APPLY; CANCEL restores the committed curve. Reset and local Undo/Redo include preset changes. Each instance saves its own committed geometry with presets/projects. The selector shows CUSTOM after manual edits, history operations or reopening; the starting-preset name is not stored separately. These are circuit-inspired static curves, not complete hardware emulations. Existing Input, Drive, Mix, Output, oversampling and DC removal remain in the processing path. Reference WAVE/HARMONICS use the same custom processing.

CREATIVE FX
- Glitch / Stutter: capture, repeat, retrigger, freeze, pitch roll and grain shuffle; separate Grid/Interval/Chance, Gate/Fade and saved Seed.
- Chop / Reverse: gate, Euclidean/random patterns and history-based reverse, with Swing/Fade. Reverse uses a previous captured segment.
- Tape / Vinyl Warp: wow/flutter, wear/dropouts, RPM warp, stop/start and granular textures. Optional crackles have separate level/mix and Input Follow; artifacts start disabled.
- Front / Back: stereo depth, tonal absorption, transient softening and early reflections, with level compensation.
- Pitch Shifter: GUITAR and LEGACY engines, whole-semitone PITCH, adjacent CENTS fine tuning and independent FORMANT. Blend a shifted layer with dry audio or use 100% FX MIX for the shifted rack signal.
- Rhythmic FX use running host PPQ/BPM or an explicitly labelled manual-tempo fallback. Captured audio refills after restore; parameters and Seed are saved.

PITCH SHIFTER
GUITAR is the default engine for new instances. PITCH selects -12 to +12 semitones in whole steps; CENTS adds -100 to +100 cents in 0.1-cent steps. Their combined extremes reach +/-13 semitones. FORMANT has its own -12 to +12 semitone range; at zero, GUITAR naturally transposes the spectrum. INPUT, MIX, OUTPUT and POWER apply once per instance.

Use a small octave-down blend to retain the original pick attack, or 100% FX MIX for the shifted signal alone. Each instance receives its rack band, not an independent full-band input. MASTER MIX and other active bands can retain original audio. Crossovers remain active even at their extreme settings.

LEGACY supports earlier continuous Pitch/Formant settings and saved Snap automation. Existing GUITAR states retain their control values. Dry/wet, POWER OFF, serial effects, parallel bands and ROUTING remain latency-aligned. Pitch-instance delay is fixed within a prepared sample-rate/oversampling configuration:
- 44.1 kHz: 29.025 ms at 1x; 29.751 ms at 2x/4x/8x.
- 48 kHz: 26.667 ms at 1x; 27.333 ms at 2x/4x/8x.
- 96 kHz: 26.667 ms at 1x; 27.000 ms at 2x/4x/8x.
These figures exclude crossovers, master stages, host buffers and the audio interface. Serial Pitch instances add their delays. The GUITAR analysis runs at host sample rate under rack oversampling, with filtered conversion around it.

RACK WORKFLOW
------------------------------------
Dynamic chains support repeated types with independent settings. There is no fixed manual chain-length limit beyond system resources. Each FX has POWER, INPUT/MIX/OUTPUT, meters, double-click default reset and RANDOM. Drag-and-drop provides a translucent card preview and destination gap.

RANDOM RACK creates 3-7 distinct effects from its established creative pool, followed by an additional limiter. Glitch / Stutter, Chop / Reverse, Tape / Vinyl Warp, Front / Back and Pitch Shifter are added manually rather than through RANDOM RACK. Individual RANDOM preserves INPUT/OUTPUT/POWER. CLEAR asks for confirmation.

SOLO/MUTE fades out and suspends the affected band's FX/oversampling, discarding old histories. Unmute starts fresh. MASTER MIX can still include the parallel dry contribution. Rack oversampling offers 1x/2x/4x/8x; delay compensation aligns serial effects, parallel bands, dry/wet and separate outputs.

MASTER AND ROUTING
------------------------------------
- Complementary linear-phase FIR crossover with adjustable split frequencies and three steepness profiles.
- Ten-point Master EQ, HP/LP and SOLO BAND in the two-row layout.
- Master Limiter: INPUT, CEILING, RELEASE, LOOKAHEAD and post-ceiling GAIN COMPENSATION.
- Limiter Waveform and compensated ceiling reference are measured before final MASTER OUTPUT; that final gain has its own peak meter.
- MASTER sends stereo to 1/2. ROUTING bypasses Master processing, silences 1/2 and sends LOW to 3/4, MID to 5/6, HIGH to 7/8.
- Enable/connect those stereo buses in the host. MMR does not create DAW tracks or sends automatically.

INTERFACE AND PRESETS
------------------------------------
- Metal panels, screws, recessed displays, rocker switches, dice controls and dedicated compressor styling.
- Effect-specific views: analogue gain reduction, drive, clipping/overdrive, attenuation, stereo correlation, transient gain and tape-speed deviation; stereo modulation, echoes, reverb tails and other dedicated displays. Cream paper dials sit inside the original recessed frames. UP/DOWN retains its separate digital boost/reduction display.
- Reference WAVE and green HARMONICS are paired for Clipper, Saturation and Distortion. Other families use relevant effect-specific displays. Tutorial distinguishes measured audio data from independently generated reference previews.
- Percentage UI SCALE readout and 25/50/75/100% shortcuts. Window width sets control scale from approximately 25% to 200%; independent window height reveals more rack/synth content without enlarging controls. Hardware rails, top crossover and synth Output Guard retain their positions.
- Mouse clicks and Enter switch FX display pages; Space no longer switches displays or opens the wavetable bank selector. Spaces remain available during text entry. Host handling of transport keys depends on the DAW.
- Subtle crossover regions over black, following split positions behind the purple spectrum trace.
- Immediate English Tutorial Mode, enabled for new instances.
- SAVE AS name entry; SAVE/DELETE and name collisions ask for confirmation.
- Recall of synth/custom banks/modulation, CUSTOM FX curves and dynamic FX counts, types, order, parameters and POWER.
- Local tab/scroll/window state restored when reopening the editor; full view-state persistence across DAW restarts is not promised.

COMPATIBILITY AND VALIDATION
------------------------------------
Windows 10/11 x64 VST3; JUCE/Projucer and Visual Studio 2026. REAPER is the primary user-test host. Product metadata is 'MMR Multiband Modular Rack', manufacturer 'DzaQ713', avoiding a duplicated suffix when the host adds the manufacturer.

Existing VST3 class IDs and automation IDs are retained. There are 1022 host parameters; extensions retain the existing parameter IDs, indices, types and ranges. The original 14 automation-slot identities remain fixed. The creative FX families have a dedicated first-instance bank per band; extra copies save independent settings without automatically obtaining separate automation banks. Six appended parameters select CUSTOM for the original Saturation/Distortion slots across the three bands. Duplicate instances save their own selection locally; curve points are saved geometry rather than host automation parameters. Additive schema-v4 state, CustomWaves format 3 and CustomShapers format 1 retain older-preset support. Older states without custom-shaper data load with CUSTOM disabled.

Native development checks cover state, DSP, factory-bank compatibility, custom editing, capture, variable blocks, displays and aligned routing. Pitch checks also cover harmonic multi-note input, an isolated MID rack at -2 semitones / 100% wet, measured delay and filtered sample-rate conversion. The owner confirmed the GUITAR processing in the tested guitar-DI setup. This does not imply that every feature or possible host configuration has completed user acceptance.

RESOURCE AND SIGNAL NOTES
------------------------------------
Long Glitch/Chop histories can use about 150 MB per instance at 48 kHz when all four oversampling engines are prepared. Higher sample rates increase this. At 96 kHz with 32-sample host buffers, measured Pitch callback peaks can exceed the available budget. Leave CPU headroom for the rest of the chain and adjust buffer size or oversampling to suit the session.

Pitch processing can change individual-note levels and the character of transients. The module latency listed above is additional to the rest of the monitoring path. Character FX are not exact hardware emulations. Protection applies at its location in the chain: later gain and positive post-ceiling compensation can exceed an earlier ceiling. No certified true-peak mastering claim is made.

No macOS/Linux/AU/AAX binary release, external wavetable import, Vital preset compatibility or user-loadable skin system is advertised.

REPORTING AN ISSUE
------------------------------------
Include MMR/Windows/DAW versions, source/engine, sample rate, buffer size, oversampling, voices/unison, output mode, reproduction steps and a relevant preset/routing description.
