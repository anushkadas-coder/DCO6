# DCO6

6-voice polyphonic VST3 synthesizer with 4-pole ladder filter, BBD stereo chorus, independent amplitude and filter ADSRs, LFO with delay, 3-band EQ, and FFT spectrum analyzer. Built from scratch in JUCE/C++.

**This is beta software. It will keep improving.**

---

## Download (no build required)

Grab the binaries from [Releases](../../releases/latest):

- `DCO6 v1.1.vst3` - load in any VST3-compatible DAW (Ableton, Reaper, FL Studio, etc.)
- `DCO6 v1.1.exe` - standalone, runs without a DAW

For the VST3: copy the `DCO6 v1.1.vst3` folder to `C:\Program Files\Common Files\VST3\` and rescan plugins in your DAW.

---

## Features

- 6-voice polyphony with polyBLEP anti-aliasing
- 4-pole Moog-style ladder filter (Huovilainen model)
- BBD stereo chorus (Mode I and II)
- LFO with delay, stereo ping-pong delay, reverb
- Independent amplitude and filter ADSRs
- 3-band EQ (low shelf 200Hz, peak 1kHz, high shelf 5kHz)
- Real-time FFT spectrum analyzer
- Light and neon skin (switchable inside the plugin)
- 8 pad presets included

### MIDI CC Mapping

Knobs:

| CC | Parameter |
|----|-----------|
| 74 | VCF Cutoff |
| 71 | VCF Resonance |
| 76 | VCF Env Amount |
| 77 | DCO PWM |
| 78 | LFO Rate |
| 84 | LFO Delay |
| 86 | Delay Mix |
| 87 | Reverb Mix |
| 88 | DCO LFO Pitch |

Faders:

| CC | Parameter |
|----|-----------|
| 73 | Filter Env Attack |
| 75 | Filter Env Decay |
| 79 | Filter Env Sustain |
| 72 | Filter Env Release |
| 80 | Amp Env Attack |
| 81 | Amp Env Decay |
| 82 | Amp Env Sustain |
| 83 | Amp Env Release |
| 85 | Volume |

---

## Building from source

### Requirements

- Windows 10/11 x64
- [Visual Studio 2022 Build Tools](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022) with "Desktop development with C++"
- [CMake 3.22+](https://cmake.org/download/)
- [Git](https://git-scm.com/)

JUCE is downloaded automatically on first build (via CMake FetchContent, needs internet).

### Steps

```bat
git clone https://github.com/jesusemans/DCO6.git
cd DCO6
build.bat
```

The script configures CMake, builds in Release mode, and auto-installs the VST3 to `C:\Program Files\Common Files\VST3\`. First build takes 5-10 minutes.

### Versioning

To release a new version (e.g. v1.2), change these two lines in `CMakeLists.txt`:

```cmake
set(DCO6_VERSION "1.2")
set(DCO6_CODE    "D612")
```

And in `build.bat`:

```bat
set VERSION=1.2
```

The 4-char plugin code must be unique per version so DAWs treat them as separate plugins.

---

## License

This project is provided as-is. No warranty. Use at your own risk.
