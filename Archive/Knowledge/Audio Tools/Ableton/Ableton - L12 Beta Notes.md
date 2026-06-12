---
tags:
  - Resource/Audio/Ableton
Author: Cody Cork
Type: Notes
Date: 2026-01-30
---
# Notes

## Some New Shortcuts to Use
- **Filter View:** Cmd Shift F (Mac)
- **Tag Editor:** Cmd Shift E (Mac)


# Auto Pan / Tremelo Updates

![[Auto Pan-Tremolo.gif|800]]

## Tremolo mode offers several distinctive traits:
- A single LFO waveform is available, which can be morphed using the Shape parameter and inverted using the Invert toggle. Exponential and linear ramp shapes are useful for gating and ducking effects.
- Harmonic mode modulates the signal level across fixed frequency bands in an alternating pattern, creating a dense, lush tremolo effect.
- Vintage mode introduces additional warmth and grit alongside the tremolo effect by modulating the intensity of a non-linear curve instead of the signal level.

Note that the original Auto Pan device remains available in the browser and has been renamed Auto Pan Legacy. When opening existing Sets that contain Auto Pan presets, the legacy device will be automatically loaded.

---


# Bounce Group Tracks 

It is now possible to bounce Group Tracks via two new commands: Bounce Group to New Track and Bounce Group in Place.

The Bounce Group to New Track command is available in the context menu for selections within group slots in Session View and within the main lane of a Group Track in Arrangement View. The Group Track is bounced with all its processing, including any return tracks used via sends from the Group Track or any of its included tracks. For that reason, bouncing is performed from the Main track, pre-FX. The bounced audio is added as a clip to a new track

Note that bouncing Group Tracks works similarly to rendering Group Tracks with the Include Return and Main Effects option, with the difference that rendering is done post-mixer on the Main track. This means that some routings may lead to silence or a partial signal, as only signals that reach Main are part of the bouncing process.


# Paste Bounced Audio

It is now possible to paste bounced audio from copied material as an alternative to using the Bounce to New Track or Bounce Group to New Track command.

To do this, first copy a clip or a clip/time selection from a MIDI, audio, or Group Track using the Copy command. Then, in an audio track, use the Paste Bounced Audio command from the track’s context menu. The copied material will be bounced and pasted onto the track.

Note that the source material will be bounced in its current state at the time Paste Bounced Audio is used. This means you can modify the material and use the command again to create variations. Additionally, if the material is deleted, Paste Bounced Audio will no longer be available.


# Device A/B Comparison

Two new entries have been added to the device title bar’s Options menu: Compare: Switch to A/B and Compare: Copy A/B to B/A.

![[Max for Live Path.png|777]]

You can use Compare: Switch to A/B to toggle between two different device states: A and B. Each state can have its own unique set of parameter values. You can, for example, use state A for tweaking values while leaving state B at the device’s default settings, and then switch between the two to assess the differences. The corresponding shortcut for comparing device states is **‘P’**

