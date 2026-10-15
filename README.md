# Multiband-Modular-Rack
Free multiband modular VST3 audio effect plugin for Windows.
MULTIBAND MODULAR RACK
Version 1.0.0 | Windows 64-bit | VST3 Audio Effect
================================================

OVERVIEW
--------
Multiband Modular Rack is a three-band audio effects processor. It divides
incoming audio into LOW, MID and HIGH frequency bands so that each band can
have its own independent, reorderable chain of effects. A Master section
provides final equalization, filtering, mixing and peak limiting.

The plugin includes an optional TUTORIAL MODE with instant, English-language
explanations of the interface controls.

KEY FEATURES
------------
* Three independent effect racks: LOW, MID and HIGH.
* Adjustable crossover frequencies and crossover slopes.
* Spectrum display with draggable crossover markers.
* Multiple effects in each rack, including dynamics, distortion, modulation,
  delay, reverb and stereo processing.
* Drag-and-drop reordering of effects within each rack.
* Per-band SOLO and MUTE controls; individual effect BYPASS controls.
* Global oversampling selection: 1x, 2x, 4x or 8x (4x by default).
* Master parametric EQ with up to 10 controllable points.
* Master high-pass and low-pass filters.
* Master dry/wet mix, output gain and peak limiter.
* User preset loading and saving.
* Adjustable interface size (UI SIZE).
* TUTORIAL MODE: contextual help appears immediately when you hover over
  interactive controls, including effect-header drag-and-drop guidance.

SYSTEM REQUIREMENTS
-------------------
* Windows 10 or Windows 11, 64-bit.
* A 64-bit DAW or audio application that supports VST3 audio effects.
* Sufficient CPU resources for your selected effects and oversampling mode.

The plugin has been tested in REAPER on Windows, including a Windows 10
computer without Visual Studio installed. Compatibility with every DAW and
hardware configuration is not guaranteed.

INSTALLATION
------------
1. Close your DAW.
2. Extract the distribution ZIP file.
3. Copy the COMPLETE folder named:

      MultibandModularRack.vst3

   into the standard Windows VST3 location:

      C:\Program Files\Common Files\VST3\

4. Restart your DAW. Rescan plugins if Multiband Modular Rack does not appear.
5. Add Multiband Modular Rack as a VST3 audio effect on a track or bus.

IMPORTANT: The .vst3 item is a folder/package. Copy the entire folder,
including its Contents subfolders. Do not rename its internal files.
Administrator approval may be required to copy files to Program Files.

QUICK START
-----------
1. Insert the plugin on an audio track or bus in your DAW.
2. Play audio and use the crossover display to set LOW / MID / HIGH bands.
3. Open the CROSSOVER + RACKS tab, enable the desired effects by unchecking
   their BYPASS boxes, and adjust their parameters.
4. Drag an effect's header up or down to change the order of processing.
5. Open MASTER OUTPUT to adjust EQ, filtering, limiter and final output.
6. Choose an oversampling setting (OS) appropriate to your CPU budget.
7. Check TUTORIAL MODE for instant help when hovering over controls.

For detailed instructions, read INSTRUCTION.txt.

PERFORMANCE NOTES
-----------------
Oversampling improves internal processing quality in suitable effects, but
higher settings use more CPU and memory. If playback becomes unstable, try
2x or 1x. Changing oversampling during playback can briefly affect effects
that retain audio history, such as delay and reverb.

PRESETS AND PROJECTS
--------------------
Use the plugin's preset controls to save and recall your settings. DAW
projects can also store the plugin's parameter state. Save your DAW project
after making changes.

UNINSTALLATION
--------------
Close your DAW and remove the MultibandModularRack.vst3 folder from the
VST3 directory. User presets and UI preferences may remain under your
Windows user application-data directory.

DISTRIBUTION NOTES
------------------
This package contains the compiled Windows VST3 plugin. Source code is not
included. For license and redistribution permissions, refer to the terms
provided by the plugin author; this README does not grant any license.

DOCUMENTATION
-------------
INSTRUCTION.txt - Installation, interface tour and detailed operating guide.
