SHORT DESCRIPTION
=====================================
Free Windows x64 VST3: three-band modular FX, a wavetable synth with custom wave editing, 23 effect families, creative randomizers and separate band outputs.

MULTIBAND MODULAR RACK — v1.5.0
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
- A Legacy synth engine and its original bank selectors are also available.

CUSTOM WAVE EDITOR
Click a modular waveform to edit a four-frame CUSTOM bank. Use up to ten points per frame, POINT selection, AMPLITUDE, Q, LEFT/RIGHT CURVE and local segment shaping. BASE PHASE and POINTS PHASE can move separately or together through LINK. Zoom, point removal, local Undo/Redo and RANDOM are available.

Draft audition uses the actual synth modulation and Position path. Accept commits; Cancel restores. Unaccepted drafts are excluded from saved host state. CUSTOM banks and geometry are saved with presets/projects. External wavetable-file import is not included.

23 EFFECT FAMILIES
------------------------------------
Clipper; Saturation; Distortion; Compression; Phaser; Chorus; Stereo Width; Limiter; Gate; Transient Shaper; Flanger; Stereo Delay; Reverb; Wah; Frequency Shifter; Ring Modulator; Comb / Resonator; Exciter; Glitch / Stutter; Chop / Reverse; Tape / Vinyl Warp; Front / Back; Pitch Shifter.

148 MODELS, THREE APPROACHES
Every family starts with MMR and SIMPLE, followed by device-inspired models. MMR is the default: an original, fully featured engine, not a selector for other engines. SIMPLE exposes a smaller practical control set. The catalogue contains 23 MMR, 23 SIMPLE and 102 other profiles. Each profile has its own controls, ranges and defaults, with independent parameter banks.

Examples include Tube/Tape/Transistor/Transformer/Console/Worn Tape/Germanium saturation; FET Fast/Opto Leveler/VCA Bus/UP-DOWN/Vari-Mu/Diode Bridge/Clean RMS compression; Bit Crush/Soft Clip/Hard Clip/Foldback/Fuzz/Rectifier/Sample Crush distortion; Barberpole/Vowel phasing; Ensemble/Dual/Vibrato chorus; Haas/Micro Detune/Mono Bass width; Room/Hall/Plate/Spring/Dual Space reverberation; and modal resonators. Other model identities include Clean Cascade, Four-Stage Sweep and Twin Intervals.

The models use original behavioural DSP inspired by hardware characteristics. They are not certified component-exact recreations. Selected profiles expose detector filtering, external sidechain, recovery, magnetic colour, modulation or feedback controls where supported.

CUSTOM SATURATION AND DISTORTION
Choose MMR in Saturation or Distortion and use EDIT CURVE to draw an input-to-output transfer curve. Add up to ten interior points plus two end points, move them or adjust their curvature. Saturation preserves a monotonic response; Distortion permits folding and rectification. This editor shapes audio amplitude, unlike the synth editor's periodic wavetable.

CURVE PRESET provides editable starting points:
- Saturation: NEUTRAL, TUBE, TAPE, CONSOLE, GERMANIUM.
- Distortion: NEUTRAL, SOFT DIODE, HARD DIODE, ASYMMETRIC FUZZ, RECTIFIER, FOLDBACK.

Audition changes before APPLY; CANCEL restores the committed curve. Reset and local Undo/Redo include preset changes. Each instance saves its own committed geometry with presets/projects. The curve-preset selector shows CUSTOM after manual edits, history operations or reopening; CUSTOM is not a separate FX model. The starting-preset name is not stored separately. These are circuit-inspired static curves, not complete hardware emulations. Existing Input, Drive, Mix, Output, oversampling and DC removal remain in the processing path. Reference WAVE/HARMONICS use the same custom processing.

CREATIVE FX
- Glitch / Stutter: capture, repeat, retrigger, freeze, pitch roll and grain shuffle; separate Grid/Interval/Chance, Gate/Fade and saved Seed.
- Chop / Reverse: gate, Euclidean/random patterns and history-based reverse, with Swing/Fade. Reverse uses a previous captured segment.
- Tape / Vinyl Warp: wow/flutter, wear/dropouts, RPM warp, stop/start and granular textures. Optional crackles have separate level/mix and Input Follow; artifacts start disabled.
- Front / Back: stereo depth, tonal absorption, transient softening and early reflections, with level compensation.
- Pitch Shifter: whole-semitone PITCH and adjacent CENTS fine tuning. MMR retains manual FORMANT; other profiles use automatic opposite-direction formant compensation at half the effective pitch. Blend a shifted layer or use 100% FX MIX for the shifted rack signal.
- Rhythmic FX use running host PPQ/BPM or an explicitly labelled manual-tempo fallback. Captured audio refills after restore; parameters and Seed are saved.

PITCH SHIFTER
MMR is the default profile. It has manual Formant and no Delay A/B controls. Other profiles apply automatic formant compensation equal to -0.5 times effective pitch, including cents: an octave down receives +6 semitones of compensation. Available controls depend on the selected model.

PITCH uses whole semitones from -12 to +12, with adjacent CENTS fine tuning. Blend in a lower octave or use 100% FX MIX for the shifted rack signal. Each instance processes its own rack band; other active bands and MASTER MIX can retain original audio.

The guitar-oriented analysis runs at host sample rate under rack oversampling, with filtered conversion around it. FFT/rotation and inactive-path optimizations reduce work without an automatic oversampling reduction or a new low-quality mode. Pitch shifting still adds latency and can be CPU-intensive, especially with many instances and small buffers. Serial instances add delay; the host receives the processing latency. Full monitoring delay also includes crossovers, master stages, host buffers and the interface.

RACK WORKFLOW
------------------------------------
Dynamic chains support repeated types with independent settings. There is no fixed manual chain-length limit beyond system resources. Each FX has INPUT/MIX/OUTPUT, meters, double-click default reset, RANDOM and S/M controls. FX SOLO auditions that effect within its rack. MUTE/bypass overrides SOLO and collapses the card; its header retains the name and accessible controls. Suppressed effects fade to latency-aligned bypass before processing is suspended. Drag-and-drop provides a translucent card preview and destination gap.

RANDOM RACK creates 3-7 distinct effect families from its established creative pool, followed by an additional limiter. Glitch / Stutter, Chop / Reverse, Tape / Vinyl Warp, Front / Back and Pitch Shifter are added manually rather than through RANDOM RACK. Models are selected across MMR, SIMPLE and hardware profiles. Individual RANDOM preserves INPUT/OUTPUT and the instance activity state. CLEAR asks for confirmation.

New effects start at MIX 100%, including duplicate and directly selected models. Restoring a saved patch retains its saved Mix. RANDOM may set a different Mix.

Numeric FX controls use linear scales shared by GUI, host and RKR; intentional choices, counters and semitone controls remain stepped. MMR Hz controls and Tape Warmth have no artificial numeric quantization. Hardware-specific reversed FET time-control direction is retained. This does not alter synth, generator or master scales.

RKR cycles eligible knobs over their full ranges for debugging. Each activation draws fresh, independently phased, unique 2-10 second periods within the plugin instance. Input, Mix, Output and Sync are excluded. Stop to retain current values; loading a state leaves RKR off.

SOLO/MUTE fades out and suspends the affected band's FX/oversampling, discarding old histories. Unmute starts fresh. MASTER MIX can still include the parallel dry contribution. Rack oversampling offers 1x/2x/4x/8x; delay compensation aligns serial effects, parallel bands, dry/wet and separate outputs.

MASTER AND ROUTING
------------------------------------
- Complementary linear-phase FIR crossover with adjustable split frequencies and three steepness profiles.
- Ten-point Master Parametric EQ with Band, Low Shelf and High Shelf shapes. Select points directly on the graph: white is active, yellow selected and grey muted but still selectable.
- Each point has Frequency, Q, base Gain and always-visible Side Boost/Mid Boost (-18 to +18 dB each). Effective gains are Gain + Side Boost and Gain + Mid Boost, up to +/-36 dB statically. Mid/Side EQ does not create stereo from mono or automatically preserve loudness.
- S / LS / B / HS / M provides Solo, shape selection and point bypass. HP/LP use stepped OFF / 12 / 24 / 48 dB/oct controls beside Frequency.
- Independent Dynamic EQ per point: Threshold -36 to 0 dBFS, continuous Ratio 0.50:1 to 12.00:1, Attack 0.10-500 ms and Release 10-3000 ms. Initial settings: OFF, 0 dBFS, 1:1, 30 ms and 100 ms; switching preserves edits.
- Dynamic detection follows the point's frequency region without cancelling anti-phase stereo. Ratios above 1 reduce that region above threshold; ratios below 1 expand it; Ratio 1 is neutral. Common Mid/Side correction is limited to +/-18 dB. Curves show the combined response and actual dynamic gain of the selected point.
- Full-width EQ graph above four compact groups: HP, selected point, Dynamic and LP, with thirteen knobs in one row.
- EQ Power OFF bypasses HP/LP, point processing and Solo Band. Limiter Power OFF bypasses its Input gain, detector, limiting and Gain Compensation while retaining alignment delay. Master Mix and final Master Output remain independent in MASTER mode.
- Inactive EQ/Limiter sections are dimmed and grayscale, with analyses stopped and graphs hidden. Settings remain editable. ROUTING replaces both panels with a DAW configuration explanation.
- Master Limiter: INPUT, CEILING, RELEASE, LOOKAHEAD and post-ceiling GAIN COMPENSATION.
- Limiter Waveform and compensated ceiling reference are measured before final MASTER OUTPUT; that final gain has its own peak meter.
- MASTER sends stereo to 1/2. ROUTING bypasses Master processing, silences 1/2 and sends LOW to 3/4, MID to 5/6, HIGH to 7/8.
- Enable/connect those stereo buses in the host. MMR does not create DAW tracks or sends automatically.

INTERFACE AND PRESETS
------------------------------------
- Embedded device-inspired panel/knob materials with runtime lighting, preserved 10px borders, hardware typography and model-specific layouts. MMR uses dark yellow/green/blue metal and logo teardrop knobs; SIMPLE uses light metal and walnut knobs. No external image folder is required.
- FX headers contain variant selection, an uppercase palette-matched name and S/M/RKR/RANDOM/remove actions. INPUT / DISPLAY / OUTPUT stays at the bottom, MIX above OUTPUT, with up to six upper knobs per row. Dedicated 320x142 layout-unit displays remain inside their original frames; card widths account for the vertical scrollbar and do not require horizontal scrolling.
- Effect-specific views: analogue gain reduction, drive, clipping/overdrive, attenuation, stereo correlation, transient gain and tape-speed deviation; stereo modulation, echoes, reverb tails and other dedicated displays. Cream paper dials sit inside the original recessed frames. UP/DOWN retains its separate digital boost/reduction display.
- Reference WAVE and green HARMONICS are paired for Clipper, Saturation and Distortion. Other families use relevant effect-specific displays. Tutorial distinguishes measured audio data from independently generated reference previews.
- Percentage UI SCALE readout and 25/50/75/100% shortcuts. Window width sets control scale from approximately 25% to 200%; independent window height reveals more rack/synth content without enlarging controls. Hardware rails, top crossover and synth Output Guard retain their positions.
- Mouse clicks and Enter switch FX display pages; Space no longer switches displays or opens the wavetable bank selector. Spaces remain available during text entry. Host handling of transport keys depends on the DAW.
- Subtle crossover regions over black, following split positions behind the purple spectrum trace.
- Immediate English Tutorial Mode, enabled for new instances.
- SAVE AS name entry; SAVE/DELETE and name collisions ask for confirmation.
- Recall of synth/custom banks/modulation, MMR transfer curves and dynamic FX counts, types, order, model banks, parameters, MUTE and SOLO.
- Local tab/scroll/window state restored when reopening the editor; full view-state persistence across DAW restarts is not promised.

COMPATIBILITY AND VALIDATION
------------------------------------
Windows 10/11 x64 VST3; JUCE/Projucer and Visual Studio 2026. REAPER is the primary user-test host. Product metadata is 'MMR Multiband Modular Rack', manufacturer 'DzaQ713', avoiding a duplicated suffix when the host adds the manufacturer.

VST3 product identity is retained. Current dynamic FX state uses schema 7 and stores per-profile banks and independent instances, including curves and Solo/Mute. Synth CUSTOM waves and transfer-curve geometry are saved separately from automatable scalar controls. Extra instances do not automatically receive unlimited separate host automation slots.

Saved physical parameter values, including Mix, are restored. Numeric FX controls use linear normalized mappings: 0.5 for a 0.02-10 Hz Rate is 5.01 Hz. Projects from versions using different engines or parameter mappings may need review; no automatic conversion of older normalized DAW automation envelopes is supplied.

Automated development checks cover the model catalogue, independent MMR processing, curve audition/commit/cancel, state recall, menu choices, UI bindings, audio stability and sample-rate/oversampling combinations. Test coverage does not imply exhaustive host or real-session validation.


RESOURCE AND SIGNAL NOTES
------------------------------------
Long Glitch/Chop histories can use about 150 MB per instance at 48 kHz when all four oversampling engines are prepared. Higher sample rates increase this. At 96 kHz with 32-sample host buffers, measured Pitch callback peaks can exceed the available budget. Leave CPU headroom for the rest of the chain and adjust buffer size or oversampling to suit the session.

Pitch processing can change individual-note levels and the character of transients. Pitch processing latency adds to the rest of the monitoring path. Character FX are not exact hardware emulations. Protection applies at its location in the chain: later gain and positive post-ceiling compensation can exceed an earlier ceiling. No certified true-peak mastering claim is made.

No macOS/Linux/AU/AAX binary release, external wavetable import, Vital preset compatibility or user-loadable skin system is advertised.

REPORTING AN ISSUE
------------------------------------
Include MMR/Windows/DAW versions, source/engine, sample rate, buffer size, oversampling, voices/unison, output mode, reproduction steps and a relevant preset/routing description.
