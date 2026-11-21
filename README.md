# Polyend OG Generators

Welcome! I build these tools to give the original (OG) Polyend Tracker a boost with more ways to make sounds. The idea is simple: choose a synthesis method, turn a few controls, and make something you can use in a track.

This collection brings together classic waveforms, FM, phase distortion, wavetable shaping, plucked strings, thick detuned sounds, drum kits and individual percussion hits. There are also effects for adding the rough edges of older samplers and game consoles.

These plugins use [Polyend Tracker CE (Community Edition)](https://github.com/polyend/tracker-ce). Thanks to Polyend and the CE community for opening up the Tracker and making projects like this possible.

A `.ptfx` file runs in the **Sample Editor**. Generators make audio that you can then play, slice, loop or use as a wavetable. You change the controls and render a new sound with Preview and Apply.

## Install

1. Use firmware with CE's `.ptfx` Sample Editor support. If you need to install or update it, start with the [Polyend Tracker CE project and its firmware instructions](https://github.com/polyend/tracker-ce). Choose the firmware for your Tracker model; this collection is aimed at the original Tracker.
2. Download this repository using **Code → Download ZIP**, then unzip it.
3. Open [Generators](Generators) or [Effects](Effects). Copy the `.ptfx` files you want into an `Effects` folder at the root of your Tracker's SD card. You can use subfolders to keep them tidy.
4. Put the card back in the Tracker. Open **Sample Editor**, go to the effect list, and choose **Load Effect...** to browse for a plugin.
5. For a generator, start with an empty instrument slot. Set its controls, listen with **Preview**, then choose **Apply**. For an effect or converter, load a sample first.
6. Save the sound as a sample or instrument when you are happy with it.

For more detail, see the official [PTFX installation and usage guide](https://github.com/polyend/tracker-ce/blob/main/docs/modular_effects_system.md). You only need the compiled `.ptfx` files to use this collection.

## Find a sound

- [Gen](#gen): 21 generators for pitched sounds, noise and wavetables.
- [Drum](#drum): 10 generators that make a whole kit in one sample chain.
- [Perc](#perc): 15 generators for making one percussion hit at a time.
- [Effects and converters](#effects-and-converters): 15 tools for cleaning up or colouring existing samples.

## Read the controls

Each plugin below has a table for each parameter page, with up to four controls per page. Use **More** on the Tracker to move through the pages. The host may also show a preset page; that is separate from the controls listed here.

**Default** is the starting value. **Values / range** lists the choices or the lowest and highest values. `st` means semitones, `cent` means one hundredth of a semitone, `ms` means milliseconds, and `Hz` means cycles per second. `ofs` means an adjustment around a style's starting setting: zero keeps that setting. Numeric step sizes are included where they are not 1. Some model names are shortened on the Tracker screen.

**WT** means wavetable: a row of short waveform frames. After Apply, check that playback is set to **Wavetable** and match the instrument's **Window** to the generator's Window. Move or modulate **Position** to travel through the frames. Window is the number of samples in each frame; Frames is how many frames are generated.

For ordinary sustained samples, set up looping in the instrument if you want the note to keep playing. A generator's Loop or Xfade control prepares the audio; check the instrument's playback settings too.

## Generation time: the coffee guide

More coffee means a longer wait for **Preview or Apply** to generate the sample. This is a **provisional workload rating**, not a sound-quality score or a playback CPU meter. Once rendered, the PTI plays the saved audio using the Tracker's instrument settings.

| Rating | Pace | Rough planning allowance per render |
| --- | --- | --- |
| ☕ (1/5) | Quick sip | Under 5 seconds |
| ☕ ☕ (2/5) | Short pause | About 5–15 seconds |
| ☕ ☕ ☕ (3/5) | A little wait | About 15–30 seconds |
| ☕ ☕ ☕ ☕ (4/5) | Put the kettle on | About 30–60 seconds |
| ☕ ☕ ☕ ☕ ☕ (5/5) | Coffee break | About 1–3 minutes or longer |

**These time bands are uncalibrated estimates, not measured OG Tracker timings.** The ratings below estimate relative work from the synthesis method and output size. Available development timings come from desktop/native or ARM-emulated renders and cannot establish a hardware wait time. Treat the bands as an initial planning guide until timed on your Tracker; a particular patch may fall outside its band.

Longer Length, Decay or Release settings, more voices, larger wavetable Windows and more Frames can increase the wait. Whole drum kits generate several sounds, and some percussion models analyse the tail and render it again. Short settings can be much quicker; heavy models and long tails can take substantially longer. Preview and Apply can each require a render, so allow for both when auditioning and committing a sound.

## What the PTI adds to the demos

The `.ptfx` creates the source audio. A `.pti` stores that audio together with playback settings: looping or slicing, wavetable position, volume envelopes, filters, modulation and any drive or bit reduction. Those settings can turn the same generated source into a pluck, a sustained bass, a moving pad or a playable kit.

Each demo below identifies the PTI contribution. **Source audition** means the linked WAV does not demonstrate a finished PTI; **PTI preview** means it uses the saved instrument settings in an offline audition. Notes describe the saved settings, while the offline renderer may only approximate their sound on the Tracker. Source selections and render processing are recorded in [demo-sources.json](Audio/demo-sources.json).

## Gen

[OSC](#osc) · [OSC WT](#osc-wt) · [PWM WT](#pwm-wt) · [FM WT](#fm-wt) · [PHASE WT](#phase-wt) · [ACID WT](#acid-wt) · [SYNC WT](#sync-wt) · [WAV WT](#wav-wt) · [STRING](#string) · [NOISE](#noise) · [BUZZ](#buzz) · [UNISON](#unison) · [FOLD WT](#fold-wt) · [STRUCK](#struck) · [FORMANT WT](#formant-wt) · [SUNSOFT](#sunsoft) · [DONK](#donk) · [HOOVER](#hoover) · [NEURO WT](#neuro-wt) · [REESE](#reese) · [SUPERSAW](#supersaw)

Choose these for basses, leads, pads, textures and sound design. WT generators build a bank of shapes; the other generators make ordinary sample audio, with SUNSOFT making a chain of notes.

### OSC

File: [`Gen_01_OSC.ptfx`](Generators/Synth/Gen_01_OSC.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). A single cycle is very small; longer sample settings take more work.

- **[Demo 1](Audio/Synth/Gen_01_OSC/Demo-1.wav) — HollowFoundation:** Source audition: no finished PTI processing is demonstrated. A PTI can sustain this source with looping and add an amplitude envelope to control the attack and note-off tail.
- **[Demo 2](Audio/Synth/Gen_01_OSC/Demo-2.wav) — BiasedFoldFlutter:** PTI preview: looping sustains the generated source; the volume envelope adds a 20 ms attack and 180 ms release; a band-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_01_OSC/Demo-3.wav) — HalfSineWoodBurnished:** PTI preview: looping sustains the generated source; the volume envelope adds a 3 ms attack and 1000 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit.

A starting point for basses, leads and chip sounds. It makes one of 16 waveforms, then lets you bend, fold, sync and reduce its resolution. Choose a single cycle or a longer sample.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Sine | Square, Pulse12.5, Pulse25, Pulse50, Pulse75, Pokey, Saw, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Trapezoid, Formant, Steps, Parabola | Chooses the starting waveform. |
| Shape | 0 | -100 to 100 | Reshapes the waveform. |
| Bit | 16 bit | 2 to 16 bit | Sets the bit resolution. Lower values sound more stepped and rough. |
| Sync | 0 | 0 to 100 | Adds oscillator-sync shaping for a sharper tone. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Ring | 0 % | 0 to 100 % | Adds ring-modulation colour for extra upper tones. |
| Fold | 0 % | 0 to 100 % | Folds the wave back on itself for extra harmonics. |
| Skew | 0 | -100 to 100 | Makes the waveform less symmetrical. |
| Crush | 0 % | 0 to 100 % | Adds coarse digital texture. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Length | Cycle | Cycle, 100ms, 500ms, 1000ms | Sets the generated sample length. |


### OSC WT

File: [`Gen_02_OSC_WT.ptfx`](Generators/Synth/Gen_02_OSC_WT.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_02_OSC_WT/Demo-1.wav) — RingCarousel:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_02_OSC_WT/Demo-2.wav) — SyncSpectrumBubble:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 3 ms attack and 100 ms release; a low-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_02_OSC_WT/Demo-3.wav) — SharkFin:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 5 ms attack and 160 ms release.

A quick way to put many basic waveforms in one instrument. It makes 16 frames, one for each waveform, with the same shaping controls applied to them all. Scan Position to change waveform.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Shape | 0 | -100 to 100 | Reshapes the waveform. |
| Bit | 16 bit | 2 to 16 bit | Sets the bit resolution. Lower values sound more stepped and rough. |
| Sync | 0 | 0 to 100 | Adds oscillator-sync shaping for a sharper tone. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Ring | 0 % | 0 to 100 % | Adds ring-modulation colour for extra upper tones. |
| Fold | 0 % | 0 to 100 % | Folds the wave back on itself for extra harmonics. |
| Skew | 0 | -100 to 100 | Makes the waveform less symmetrical. |
| Crush | 0 % | 0 to 100 % | Adds coarse digital texture. |


### PWM WT

File: [`Gen_03_PWM_WT.ptfx`](Generators/Synth/Gen_03_PWM_WT.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_03_PWM_WT/Demo-1.wav) — SharkBite:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_03_PWM_WT/Demo-2.wav) — ElasticSquareBubble:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 3 ms attack and 100 ms release; a band-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_03_PWM_WT/Demo-3.wav) — TriangularDewCeremony:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 1 ms attack and 1200 ms release; a low-pass filter shapes the frequency balance.

For hollow, moving leads and basses. It changes the width of the selected wave across a wavetable, then adds optional folding and drive.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Square | Square, Sine, Triangle, Saw, Shark, Trapezoid, FoldSine | Chooses the starting waveform. |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Fold | 0 | 0 to 255 | Adds folding after the width change; higher values add more harmonics. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |


### FM WT

File: [`Gen_04_FM_WT.ptfx`](Generators/Synth/Gen_04_FM_WT.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_04_FM_WT/Demo-1.wav) — FeedbackCoil:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_04_FM_WT/Demo-2.wav) — FeedbackWireDrill:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope keeps the attack immediate and sets a 90 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit; 10-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_04_FM_WT/Demo-3.wav) — BasaltChoirFilament:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 500 ms attack and 1400 ms release; a high-pass filter moves with modulation to reshape brightness; 11-bit playback adds digital grain.

For bells, bright basses and metallic digital tones. One oscillator bends the phase of another, giving an FM-style sound. The amount can change across the wavetable. C means carrier, the main tone; M means modulator, the wave shaping it.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| C Wave | Sine | Sine, Triangle, Saw, Square, Pulse25 | Waveform of the main tone. |
| C Ratio | 1 x | 0.5 to 8 x; step 0.25 | Main oscillator frequency relative to the base. |
| C Phase | 0 cyc | 0 to 1 cyc; step 0.01 | Starting position within the main wave cycle. |
| C Feed | 0 | 0 to 4; step 0.05 | Adds feedback-like phase shaping to the carrier. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| M Wave | Sine | Sine, Triangle, Saw, Square, Pulse25 | Waveform used to shape the main tone. |
| M Ratio | 2 x | 0.5 to 8 x; step 0.25 | Modulator frequency relative to the base. |
| M Index | 0 rad | 0 to 16 rad; step 0.1 | Starting modulation strength. Higher values add more upper tones. |
| M Sweep | 8 rad | -16 to 16 rad; step 0.1 | Change in modulation strength from the first frame to the last. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| M Shape | 0 % | -100 to 100 % | Reshapes the modulating waveform. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |


### PHASE WT

File: [`Gen_05_PHASE_WT.ptfx`](Generators/Synth/Gen_05_PHASE_WT.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_05_PHASE_WT/Demo-1.wav) — Classic Saw:** Source audition: no PTI is used. The preview adds a three-second linear wavetable scan and short fades; a PTI Position envelope or LFO can provide similar movement during playback.
- **[Demo 2](Audio/Synth/Gen_05_PHASE_WT/Demo-2.wav) — Classic Res1:** Source audition: no PTI is used. The preview adds a three-second linear wavetable scan and short fades; a PTI Position envelope or LFO can provide similar movement during playback.
- **[Demo 3](Audio/Synth/Gen_05_PHASE_WT/Demo-3.wav) — Extended Formant:** Source audition: no PTI is used. The preview adds a three-second linear wavetable scan and short fades; a PTI Position envelope or LFO can provide similar movement during playback.

For sharp digital basses, glassy tones and unusual moving shapes. It reshapes the timing within each wave cycle using 32 phase-shaping modes. Family chooses the left or right half of each paired Mode name. Some modes do not use every shaping control.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Family | Classic | Classic, Extended | Classic uses the left Mode name; Extended uses the right. |
| Mode | Saw/Formnt | Saw/Formnt, Sqr/Harmon, Pulse/Spec, Dbl/Window, SawPl/Sync, Res1/Ring, Res2/FM-PD, Res3/BitPh, Tri/Morph, PWM/Vector, Fold/Cross, Wrap/Chaos, Skew/Step, Bend/Motn, Pinch/Tab, Mirror/Drw | Chooses the phase-shaping method within the selected Family. |
| Shape | 50 % | 0 to 100 % | Changes the selected mode's shape; its effect depends on Mode. |
| Morph | 50 % | 0 to 100 % | Changes a second part of the selected mode; some modes ignore it. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Depth | 0 % | 0 to 100 % | Starting strength of phase shaping. Zero starts from a sine wave. |
| Sweep | 100 % | -100 to 100 % | Change in shaping depth across the frames; zero repeats one shape. |
| Motion | 0 cyc | 0 to 1 cyc; step 0.01 | Fixed motion phase for the Chaos and Motion modes. |
| Cross | 0 % | 0 to 100 % | Amount of the extra sine input used by CrossPd and Chaos. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Phase | 0 cyc | 0 to 1 cyc; step 0.01 | Rotates every waveform frame within its cycle. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |


### ACID WT

File: [`Gen_06_ACID_WT.ptfx`](Generators/Synth/Gen_06_ACID_WT.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_06_ACID_WT/Demo-1.wav) — DualAcidEngine:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_06_ACID_WT/Demo-2.wav) — CharcoalDust:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope keeps the attack immediate and sets a 160 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit; 4-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_06_ACID_WT/Demo-3.wav) — DistantCurrentWeather:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 800 ms attack and 2000 ms release; a high-pass filter moves with modulation to reshape brightness; 9-bit playback adds digital grain.

For squelchy acid bass and resonant leads. Saw and pulse sources feed a resonant filter-style sound, with different brightness sweeps spread across the wavetable.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Saw | Saw, Pulse, S+P, Saw+Sub, Pulse+Sub, S+P+S | Chooses the starting waveform. |
| Shape | 128 | 0 to 255 | Changes pulse width or the balance of the selected source waves. |
| Reso | 210 | 0 to 255 | Strength of the resonant peak: higher values sound more squelchy. |
| Bite | 30 | 0 to 255 | Adds edge to the acid tone. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Sweep | Wide | Dark, Bass, Wide, Bright, Accent, All | Selects the range and character of the filter-colour sweep. |
| Drive | 1.7 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |


### SYNC WT

File: [`Gen_07_SYNC_WT.ptfx`](Generators/Synth/Gen_07_SYNC_WT.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_07_SYNC_WT/Demo-1.wav) — ResetHammer:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_07_SYNC_WT/Demo-2.wav) — SharkAnchorAir:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 500 ms attack and 800 ms release; a high-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_07_SYNC_WT/Demo-3.wav) — SawCathedralCavern:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 1700 ms attack and 2300 ms release; a low-pass filter moves with modulation to reshape brightness.

For cutting leads and tearing basses. It combines two waveforms with oscillator sync: one wave is repeatedly restarted by another. The sync movement is written into the frames.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave A | Saw | Square, Pulse12.5, Pulse25, Pulse50, Pulse75, Pokey, Saw, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Trapezoid, Formant, Steps, Parabola | Chooses the first waveform. |
| Wave B | Saw | Square, Pulse12.5, Pulse25, Pulse50, Pulse75, Pokey, Saw, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Trapezoid, Formant, Steps, Parabola | Chooses the synced waveform. |
| Ratio | 16x | 2x, 4x, 8x, 16x | Sets the upper sync ratio used by the sweep. |
| Balance | 75 % | 0 to 100 % | Mix of the two oscillator parts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Fold | 0 | 0 to 255 | Folds the wave back on itself for extra harmonics. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Path | Rise | Rise, Fall, Curve Up, Curve Down, Rise Fall, Flat | Controls the direction and curve of change across the frames. |


### WAV WT

File: [`Gen_08_WAV_WT.ptfx`](Generators/Synth/Gen_08_WAV_WT.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_08_WAV_WT/Demo-1.wav) — SquareToShark:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_08_WAV_WT/Demo-2.wav) — ParabolaRaspFlicker:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 2 ms attack and 120 ms release; a high-pass filter moves with modulation to reshape brightness; 6-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_08_WAV_WT/Demo-3.wav) — HalfMoonGlassFrost:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 1 ms attack and 850 ms release; a high-pass filter shapes the frequency balance; 12-bit playback adds digital grain.

For sounds that change from one custom shape into another. Set the start and end waveforms, wrapping, phase and folding; the generator fills in the frames between them. S means start and E means end.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave S | Saw | Square, Pulse12.5, Pulse25, Pulse50, Pulse75, Pokey, Saw, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Trapezoid, Formant, Steps, Parabola | Waveform at the start of the wavetable. |
| Wrap S | 0 | 0 to 255 | Amount of wave wrapping at the start of the wavetable. |
| Phase S | 0 | 0 to 255 | Phase offset at the start of the wavetable. |
| Fold S | 0 | 0 to 255 | Amount of wavefolding at the start of the wavetable. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave E | Saw | Square, Pulse12.5, Pulse25, Pulse50, Pulse75, Pokey, Saw, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Trapezoid, Formant, Steps, Parabola | Waveform at the end of the wavetable. |
| Wrap E | 160 | 0 to 255 | Amount of wave wrapping at the end of the wavetable. |
| Phase E | 128 | 0 to 255 | Phase offset at the end of the wavetable. |
| Fold E | 48 | 0 to 255 | Amount of wavefolding at the end of the wavetable. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |
| Path | Rise | Rise, Fall, Curve Up, Curve Down, Rise Fall, Flat | Controls the direction and curve of change across the frames. |


### STRING

File: [`Gen_09_STRING.ptfx`](Generators/Synth/Gen_09_STRING.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_09_STRING/Demo-1.wav) — NylonStarlight:** Source audition: the attack and timbre come from the generated sample, with no finished PTI processing demonstrated. A PTI can add playback tuning, filtering and a note envelope.
- **[Demo 2](Audio/Synth/Gen_09_STRING/Demo-2.wav) — WirePluckDust:** PTI preview: looping sustains the generated source; the volume envelope keeps the attack immediate and sets a 160 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit; 4-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_09_STRING/Demo-3.wav) — BowedLinenSoftHorizon:** PTI preview: looping sustains the generated source; the volume envelope adds a 2300 ms attack and 2600 ms release; a low-pass filter moves with modulation to reshape brightness.

For plucks and vintage string-machine pads. Plucked uses a vibrating-string model; Bowed layers filtered saw waves with an ensemble effect for a soft string-like sound.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Plucked | Plucked, Bowed | Chooses a plucked or bowed string-like sound. |
| Timbre | 55 % | 0 to 100 % | Changes pluck excitation brightness or the Bowed filter brightness. |
| Color | 40 % | 0 to 100 % | Changes pluck damping and colour; in Bowed mode, adds octave brightness and ensemble movement. |
| Decay | 1500 ms | 100 to 3000 ms; step 10 | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Attack | 5 ms | 0 to 500 ms | Sets how gradually the sound starts. |
| Detune | 0 cent | 0 to 40 cent | Pitch spacing between voices. Higher values create stronger beating. |
| Xfade | 0 ms | 0 to 100 ms | Blends the sample ends to help make a smoother loop. |
| Length | 2 s | 0.5 s, 1 s, 2 s | Sets the generated sample length. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


### NOISE

File: [`Gen_10_NOISE.ptfx`](Generators/Synth/Gen_10_NOISE.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_10_NOISE/Demo-1.wav) — ParticleVeil:** Source audition: the attack and timbre come from the generated sample, with no finished PTI processing demonstrated. A PTI can add playback tuning, filtering and a note envelope.
- **[Demo 2](Audio/Synth/Gen_10_NOISE/Demo-2.wav) — MetalWindAir:** PTI preview: looping sustains the generated source; the volume envelope adds a 500 ms attack and 800 ms release; a high-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_10_NOISE/Demo-3.wav) — GustHorizonAirwash:** PTI preview: looping sustains the generated source; the volume envelope adds a 1600 ms attack and 2200 ms release; a high-pass filter shapes the frequency balance.

For hiss, wind, crackle, percussion layers and effects. It makes different kinds of random or clocked noise, with colour and rate controls and an optional sweep.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Mode | White | White, Pink, Brown, Twin Peak, Particle, Crackle, Metallic, Wind, NES Long, NES Short, Clocked | Chooses the noise or buzzing source. |
| Color | 50 | 0 to 100 | Changes the sound from darker to brighter or changes its noise colour. |
| Rate | 100 | 0 to 100 | Sets the noise clock or event rate. |
| Length | 2000 ms | 100 ms, 250 ms, 500 ms, 1000 ms, 2000 ms | Sets the generated sample length. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sweep | 50 % | 0 to 100 % | Sweeps the selected target over the sample; 50 is neutral. |
| Target | Rate | Rate, Color, Both | Chooses whether the sweep changes rate, colour or both. |
| Xfade | 0 ms | 0 to 100 ms | Blends the sample ends to help make a smoother loop. |
| Seed | 0 | 0 to 255 | Selects a repeatable noise or variation pattern. |


### BUZZ

File: [`Gen_11_BUZZ.ptfx`](Generators/Synth/Gen_11_BUZZ.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_11_BUZZ/Demo-1.wav) — BuzzMetal:** Source audition: the attack and timbre come from the generated sample, with no finished PTI processing demonstrated. A PTI can add playback tuning, filtering and a note envelope.
- **[Demo 2](Audio/Synth/Gen_11_BUZZ/Demo-2.wav) — MetalHarmonics:** PTI preview: looping sustains the generated source; the volume envelope adds a 2 ms attack and 90 ms release.
- **[Demo 3](Audio/Synth/Gen_11_BUZZ/Demo-3.wav) — VelvetBass:** PTI preview: looping sustains the generated source; the volume envelope adds a 250 ms attack and 350 ms release.

For pitched noise, rough bass and chip-like textures. It uses the noise family with a frequency control, so you can steer its buzzing or clocked character toward a note. Not every noise mode has a clear musical pitch.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Mode | NES Short | White, Pink, Brown, Twin Peak, Particle, Crackle, Metallic, Wind, NES Long, NES Short, Clocked | Chooses the noise or buzzing source. |
| Color | 50 | 0 to 100 | Changes the sound from darker to brighter or changes its noise colour. |
| Freq | 523.25113 Hz | 20 to 2000 Hz | Sets the main frequency or noise clock pitch. |
| Length | 2000 ms | 100 ms, 250 ms, 500 ms, 1000 ms, 2000 ms | Sets the generated sample length. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sweep | 50 % | 0 to 100 % | Sweeps the selected target over the sample; 50 is neutral. |
| Target | Freq | Freq, Color, Both | Chooses whether the sweep changes frequency, colour or both. |
| Xfade | 0 ms | 0 to 100 ms | Blends the sample ends to help make a smoother loop. |
| Seed | 0 | 0 to 255 | Selects a repeatable noise or variation pattern. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


### UNISON

File: [`Gen_12_UNISON.ptfx`](Generators/Synth/Gen_12_UNISON.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Layered oscillators and longer samples increase the work.

- **[Demo 1](Audio/Synth/Gen_12_UNISON/Demo-1.wav) — PulseEnsemble:** Source audition: no finished PTI processing is demonstrated. A PTI can sustain this source with looping and add an amplitude envelope to control the attack and note-off tail.
- **[Demo 2](Audio/Synth/Gen_12_UNISON/Demo-2.wav) — TriangleEnsembleTelephone:** PTI preview: looping sustains the generated source; the volume envelope adds a 8 ms attack and 130 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit; 8-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_12_UNISON/Demo-3.wav) — CurvedStringsHollowWaves:** PTI preview: looping sustains the generated source; the volume envelope adds a 900 ms attack and 1800 ms release; a band-pass filter moves with modulation to reshape brightness.

For thick leads, basses and pads. It stacks copies of a waveform at slightly different pitches, then blends them with a central voice and optional sub tone.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Saw | Saw, Saw Down, Square, Pulse12.5, Pulse25, Pulse75, Triangle, Sharktooth, Sine, Half Sine, Rect Sine, Fold Sine, Trapezoid, Formant, Steps, Parabola | Chooses the starting waveform. |
| Voices | 7 | 1, 2, 3, 5, 7 | Number of stacked oscillators. |
| Detune | 12 cent | 0 to 40 cent | Pitch spacing between voices. Higher values create stronger beating. |
| Blend | 60 % | 0 to 100 % | Balances the central voice against the detuned voices. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sub | 0 % | 0 to 100 % | Adds a lower tone for more weight. |
| Length | 2 s | 0.5 s, 1 s, 2 s | Sets the generated sample length. |
| Loop | Xfade | Xfade, Periodic | Xfade blends the loop join; Periodic fits the oscillators to a repeating sample. |
| Phase | 70 % | 0 to 100 % | Changes starting phase or the spread of starting phases. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


### FOLD WT

File: [`Gen_13_FOLD_WT.ptfx`](Generators/Synth/Gen_13_FOLD_WT.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_13_FOLD_WT/Demo-1.wav) — FoldSawClaw:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_13_FOLD_WT/Demo-2.wav) — RectifiedRootSnap:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope keeps the attack immediate and sets a 65 ms release; a low-pass filter moves with modulation to reshape brightness; overdrive adds grit.
- **[Demo 3](Audio/Synth/Gen_13_FOLD_WT/Demo-3.wav) — ParabolicFlareWeather:** PTI preview: an LFO moves through the wavetable for changing tone; the volume envelope adds a 800 ms attack and 2000 ms release; a high-pass filter moves with modulation to reshape brightness; 9-bit playback adds digital grain.

For bright, rough or metallic tones. Wavefolding bends peaks back on themselves to add extra harmonics. The wavetable follows the selected folding path.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Sine | Sine, Triangle, Saw, Sharktooth, Half Sine, Rect Sine, Trapezoid, Formant, Parabola, Organ | Chooses the starting waveform. |
| Fold | 2 | 0 to 7; step 0.05 | Folds the wave back on itself for extra harmonics. |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Bias | 0 % | -100 to 100 % | Offsets the waveform entering the folder, changing its symmetry. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |
| Path | Fall | Rise, Fall, Curve Up, Curve Down, Rise Fall, Flat | Controls the direction and curve of change across the frames. |


### STRUCK

File: [`Gen_14_STRUCK.ptfx`](Generators/Synth/Gen_14_STRUCK.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_14_STRUCK/Demo-1.wav) — ResonatorStone:** Source audition: the attack and timbre come from the generated sample, with no finished PTI processing demonstrated. A PTI can add playback tuning, filtering and a note envelope.
- **[Demo 2](Audio/Synth/Gen_14_STRUCK/Demo-2.wav) — HardExcitation:** PTI preview: one-shot playback preserves the generated hit; the volume envelope adds a 1 ms attack and 260 ms release.
- **[Demo 3](Audio/Synth/Gen_14_STRUCK/Demo-3.wav) — BambooKey:** PTI preview: one-shot playback preserves the generated hit; the volume envelope keeps the attack immediate and sets a 20 ms release.

For plucked, struck-string notes and tuned accents. A short noise excitation circulates through a tuned delay loop, with damping and decay making the vibration fade.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Excite | 55 % | 0 to 100 % | Changes the brightness of the noise that starts the string vibrating. |
| Damp | 40 % | 0 to 100 % | Damps upper ringing tones; more damping gives a duller sound. |
| Decay | 1200 ms | 100 to 1800 ms; step 10 | Sets how long the sound takes to fade. |


### FORMANT WT

File: [`Gen_15_FORMANT_WT.ptfx`](Generators/Synth/Gen_15_FORMANT_WT.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_15_FORMANT_WT/Demo-1.wav) — VocalGlass:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_15_FORMANT_WT/Demo-2.wav) — ThroatBassAir:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 500 ms attack and 800 ms release; a high-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_15_FORMANT_WT/Demo-3.wav) — CurvedChantTide:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 2000 ms attack and 2500 ms release; a low-pass filter moves with modulation to reshape brightness.

For vowel-like leads and talking basses. It shapes a waveform around vocal-style resonances and lays out the changing vowel colour across a wavetable.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Saw | Saw, Square, Pulse12.5, Pulse25, Triangle, Sharktooth, Trapezoid, Parabola, Fold Sine | Chooses the starting waveform. |
| Width | 100 % | 50 to 200 % | Width of the vocal-style resonance bands. |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Fold | 0 | 0 to 255 | Folds the wave back on itself for extra harmonics. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |
| Bass | 0 dB | 0 to 12 dB | Boosts the low end. |
| High | 0 dB | 0 to 12 dB | Boosts the high end. |


### SUNSOFT

File: [`Gen_16_SUNSOFT.ptfx`](Generators/Synth/Gen_16_SUNSOFT.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_16_SUNSOFT/Demo-1.wav) — Note chain 1:** Source audition: no PTI processing is added; the pitched note chain comes from the generator. A sliced PTI can make the individual notes separately playable. The WAV only adds trailing silence.
- **[Demo 2](Audio/Synth/Gen_16_SUNSOFT/Demo-2.wav) — Note chain 2:** Source audition: no PTI processing is added; the pitched note chain comes from the generator. A sliced PTI can make the individual notes separately playable. The WAV only adds trailing silence.
- **[Demo 3](Audio/Synth/Gen_16_SUNSOFT/Demo-3.wav) — Note chain 3:** Source audition: no PTI processing is added; the pitched note chain comes from the generator. A sliced PTI can make the individual notes separately playable. The WAV only adds trailing silence.

For crunchy game-style bass notes. It repitches an embedded sample into a chosen scale and passes each note through NES-style DPCM conversion. It makes a note chain, not a wavetable. Use Equal Slice: Chromatic = 12, Major/Minor/Dorian = 7, pentatonic scales = 5, Blues = 6. Reslice after changing Scale.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Root | C | C, C#, D, D#, E, F, F#, G, G#, A, A#, B | Root note of the generated note chain. |
| Octave | 2 | 1 to 4 | Octave of the root note. |
| Scale | CHROMATIC | CHROMATIC, MAJOR, MINOR, PENTA MAJ, PENTA MIN, BLUES, DORIAN | Notes included in the chain. Match Equal Slice to its note count. |


### DONK

File: [`Gen_17_DONK.ptfx`](Generators/Synth/Gen_17_DONK.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Longer generated samples and more complex models increase the work.

- **[Demo 1](Audio/Synth/Gen_17_DONK/Demo-1.wav) — DonkVessel:** Source audition: the attack and timbre come from the generated sample, with no finished PTI processing demonstrated. A PTI can add playback tuning, filtering and a note envelope.
- **[Demo 2](Audio/Synth/Gen_17_DONK/Demo-2.wav) — RubberDonk:** PTI preview: one-shot playback preserves the generated hit; the volume envelope adds a 2 ms attack and 90 ms release.
- **[Demo 3](Audio/Synth/Gen_17_DONK/Demo-3.wav) — CopperThud:** PTI preview: one-shot playback preserves the generated hit; the volume envelope keeps the attack immediate and sets a 20 ms release.

For short, knocking bass notes. A decaying FM-style tone is mixed with a low body and pitch punch, then driven for extra bite.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tone | 35 % | 0 to 100 % | Changes the sustained FM colour. |
| Knock | 65 % | 0 to 100 % | Strength of the short, knocking modulation at the start. |
| Decay | 90 ms | 15 to 400 ms | Fade time of the knocking part. |
| Ratio | 2 x | 1 to 8 x | Frequency ratio of the modulator to the main tone. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Punch | 20 % | 0 to 100 % | Changes the kick's initial pitch movement and impact. |
| Body | 30 % | 0 to 100 % | Adds weight to the lower body. |
| Drive | 6.23508 dB | 0 to 18.0618 dB; step 0.1 | Adds saturation and a rougher edge. |
| Length | 450 ms | 80 to 2000 ms; step 10 | Sets the generated sample length. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


### HOOVER

File: [`Gen_18_HOOVER.ptfx`](Generators/Synth/Gen_18_HOOVER.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ ☕ (5/5)** — provisional allowance: about 1–3 minutes or longer; see the [coffee guide](#generation-time-the-coffee-guide). Layered oscillators and longer samples increase the work.

- **[Demo 1](Audio/Synth/Gen_18_HOOVER/Demo-1.wav) — HooverTurbine:** Source audition: no finished PTI processing is demonstrated. A PTI can sustain this source with looping and add an amplitude envelope to control the attack and note-off tail.
- **[Demo 2](Audio/Synth/Gen_18_HOOVER/Demo-2.wav) — SlowVacuumGrowl:** PTI preview: looping sustains the generated source; the volume envelope adds a 2 ms attack and 110 ms release; a band-pass filter moves with modulation to reshape brightness; overdrive adds grit; 11-bit playback adds digital grain.
- **[Demo 3](Audio/Synth/Gen_18_HOOVER/Demo-3.wav) — HooverReed:** PTI preview: looping sustains the generated source; the volume envelope adds a 5 ms attack and 160 ms release.

For buzzing rave leads and thick basses. Moving pulse widths, linked saw/pulse waves, a sub tone and a chorus-like layer build a changing mono sample.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| PWM | 75 % | 0 to 100 % | Depth of pulse-width movement. |
| Rate | 30 % | 0 to 100 % | Speed of pulse-width movement. |
| Width | 50 % | 0 to 100 % | Centre pulse width around which PWM moves. |
| Mix | 50 % | 0 to 100 % | Moves from the notched saw toward the pulse wave. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sub | 45 % | 0 to 100 % | Adds a lower tone for more weight. |
| Length | 2 s | 0.5 s, 1 s, 2 s | Sets the generated sample length. |
| Loop | Xfade | Xfade, Periodic | Xfade blends the loop join; Periodic fits the oscillators to a repeating sample. |
| Chorus | 65 % | 0 to 100 % | Amount of the chorus-like thickening layer. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| RateMap | Linear | Linear, Log | Chooses linear or logarithmic response for Rate. |


### NEURO WT

File: [`Gen_19_NEURO_WT.ptfx`](Generators/Synth/Gen_19_NEURO_WT.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ ☕ (5/5)** — provisional allowance: about 1–3 minutes or longer; see the [coffee guide](#generation-time-the-coffee-guide). Window × Frames sets the output size; shaping complexity also affects the wait.

- **[Demo 1](Audio/Synth/Gen_19_NEURO_WT/Demo-1.wav) — CombCrawler:** Source audition: the preview scans the generated wavetable; no finished PTI processing is demonstrated. A PTI can store Position modulation and an amplitude envelope to make that changing tone playable.
- **[Demo 2](Audio/Synth/Gen_19_NEURO_WT/Demo-2.wav) — WideJawBloom:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 180 ms attack and 500 ms release; a low-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_19_NEURO_WT/Demo-3.wav) — FoldSquish:** PTI preview: an envelope moves through the wavetable for changing tone; the volume envelope adds a 2 ms attack and 90 ms release.

For growling basses and aggressive moving textures. It combines Reese and FM-style sources with phase spreading, folding and distortion. Motion chooses how the colour changes across the frames.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Engine | Hybrid | Reese, FM, Hybrid, FM Noise | Chooses Reese, FM or a mixture as the source. |
| Shape | 110 | 0 to 255 | Changes the selected engine's source shape. |
| Growl | 150 | 0 to 255 | Adds growling upper-tone movement. |
| Sub | 45 % | 0 to 100 % | Adds a lower tone for more weight. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Dispers | 90 | 0 to 255 | Spreads the phase of the harmonics for a smeared, hollow texture. |
| Fold | 55 | 0 to 255 | Folds the wave back on itself for extra harmonics. |
| Drive | 5 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |
| Tone | 180 | 0 to 255 | Controls the brightness after the shaping stages. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Window | 128 | 32, 64, 128, 256, 512 | Samples in each wavetable frame. Match this in the instrument playback settings. |
| Frames | 128 | 16, 32, 64, 128 | Number of waveform frames in the wavetable. |
| Motion | Roll | Roll, Snarl, Vowel, Scrape, Comb, Squish | Pattern of timbre movement across the wavetable. |
| Depth | 180 | 0 to 255 | Strength of the selected movement. |


### REESE

File: [`Gen_20_REESE.ptfx`](Generators/Synth/Gen_20_REESE.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Layered oscillators and longer samples increase the work.

- **[Demo 1](Audio/Synth/Gen_20_REESE/Demo-1.wav) — ReeseSquare:** Source audition: no finished PTI processing is demonstrated. A PTI can sustain this source with looping and add an amplitude envelope to control the attack and note-off tail.
- **[Demo 2](Audio/Synth/Gen_20_REESE/Demo-2.wav) — ReesePulseBubble:** PTI preview: looping sustains the generated source; the volume envelope adds a 3 ms attack and 100 ms release; a low-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_20_REESE/Demo-3.wav) — SevenPulseSwarm:** PTI preview: looping sustains the generated source; the volume envelope adds a 2 ms attack and 90 ms release.

For rolling, beating basses. Detuned oscillators interfere with one another, making the sound rise and fall in strength. Blend and Sub control its weight.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Wave | Saw | Saw, Square, Pulse25, Pulse12, Triangle, Sine, Shark | Chooses the starting waveform. |
| Voices | 2 | 1, 2, 3, 5, 7 | Number of stacked oscillators. |
| Detune | 15 cent | 0 to 40 cent | Pitch spacing between voices. Higher values create stronger beating. |
| Blend | 100 % | 0 to 100 % | Balances the central voice against the detuned voices. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sub | 25 % | 0 to 100 % | Adds a lower tone for more weight. |
| Length | 2 s | 0.5 s, 1 s, 2 s | Sets the generated sample length. |
| Loop | Xfade | Xfade, Periodic | Xfade blends the loop join; Periodic fits the oscillators to a repeating sample. |
| Phase | 70 % | 0 to 100 % | Changes starting phase or the spread of starting phases. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


### SUPERSAW

File: [`Gen_21_SUPERSAW.ptfx`](Generators/Synth/Gen_21_SUPERSAW.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ ☕ (5/5)** — provisional allowance: about 1–3 minutes or longer; see the [coffee guide](#generation-time-the-coffee-guide). Layered oscillators and longer samples increase the work.

- **[Demo 1](Audio/Synth/Gen_21_SUPERSAW/Demo-1.wav) — AnthemSeven:** Source audition: no finished PTI processing is demonstrated. A PTI can sustain this source with looping and add an amplitude envelope to control the attack and note-off tail.
- **[Demo 2](Audio/Synth/Gen_21_SUPERSAW/Demo-2.wav) — SevenSawAirBloom:** PTI preview: looping sustains the generated source; the volume envelope adds a 180 ms attack and 500 ms release; a low-pass filter moves with modulation to reshape brightness.
- **[Demo 3](Audio/Synth/Gen_21_SUPERSAW/Demo-3.wav) — SevenfoldDawnSoftHorizon:** PTI preview: looping sustains the generated source; the volume envelope adds a 2300 ms attack and 2600 ms release; a low-pass filter moves with modulation to reshape brightness.

For large leads, chords and pads. It stacks detuned saw waves around a central voice. Brightness and Blend let you move from a clearer tone to a dense, moving sound.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Bright | 100 % | 0 to 100 % | Brightness of the saw stack. Lower values soften the top end. |
| Voices | 7 | 1, 2, 3, 5, 7 | Number of stacked oscillators. |
| Detune | 20.25 cent | 0 to 100 cent; step 0.25 | Pitch spacing between voices. Higher values create stronger beating. |
| Blend | 75 % | 0 to 100 % | Balances the central voice against the detuned voices. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Sub | 0 % | 0 to 100 % | Adds a lower tone for more weight. |
| Length | 2 s | 0.5 s, 1 s, 2 s | Sets the generated sample length. |
| Loop | Xfade | Xfade, Periodic | Xfade blends the loop join; Periodic fits the oscillators to a repeating sample. |
| Phase | 70 % | 0 to 100 % | Changes starting phase or the spread of starting phases. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |


## Drum

[BASE](#base) · [TONE](#tone) · [CHIP](#chip) · [FM](#fm) · [PHASE](#phase) · [SIX](#six) · [SEVEN](#seven) · [EIGHT](#eight) · [NINE](#nine) · [WAVE](#wave)

These make a kit as one sample chain. After Apply, choose **Beat Slice**, use **Equal Slice** with the number at the end of the Kit name, and turn off slice play-through. Reslice whenever you change Kit. These plugins make the audio; they do not place slice markers for you.

A 4-piece layout leaves more room per hit than an 8-piece layout. Kit names and slot order can differ between engines; see the [drum slot map](docs/generator-improvements/drum-slot-map.md) for the exact contents and order.


### BASE

File: [`Gen_Drum_1_Base.ptfx`](Generators/Drum/Gen_Drum_1_Base.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_1_Base/Demo-1.wav) — BasePunch:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_1_Base/Demo-2.wav) — BaseCircuit:** PTI preview: Beat Slice maps 6 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_1_Base/Demo-3.wav) — SoftMachines:** PTI preview: Beat Slice maps 6 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 50 ms release.

For a useful everyday electronic kit. Sine-wave bodies, noise bursts and metallic pulse waves make kicks, snares, claps, hats and other percussion.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Clap4, Basic6, Toms6, Basic8, Classic8 | Chooses the kit layout; the number in its name is the slice count. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |
| Color | 0 | -100 to 100 | Changes the sound from darker to brighter or changes its noise colour. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Punch | 50 % | 0 to 100 % | Changes the kick's initial pitch movement and impact. |
| Snap | 70 % | 0 to 100 % | Changes the snare/clap attack and noisy snap. |
| Grain | 39 % | 0 to 100 % | Moves the hats from metallic pulses toward filtered noise. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### TONE

File: [`Gen_Drum_2_Tone.ptfx`](Generators/Drum/Gen_Drum_2_Tone.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_2_Tone/Demo-1.wav) — ToneHybrid:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_2_Tone/Demo-2.wav) — HybridTone:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_2_Tone/Demo-3.wav) — BentComponents:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.

For drum-machine sounds with a digital edge. It blends analog-style tones and noise with stepped, low-resolution digital voices. Style gives you a starting sound; the other controls reshape it.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Toms8, Metal4, Extra8 | Chooses the kit layout; the number in its name is the slice count. |
| Style | TONE | COMPU, CALC, TONE, BENT | Chooses a starting character for the whole kit. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Hybrid | 0 ofs | -100 to 100 ofs | Moves the style toward its analog or digital layer. |
| BD Tone | 0 ofs | -100 to 100 ofs | Changes bass drum colour. |
| Snap | 0 ofs | -100 to 100 ofs | Changes the snare/clap attack and noisy snap. |
| Metal | 0 ofs | -100 to 100 ofs | Changes the metallic colour of hats and percussion. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Cymtone | 0 ofs | -100 to 100 ofs | Changes cymbal brightness. |
| Perctun | 0 st | -12 to 12 st | Tunes the selected percussion voices separately. |
| Hat Dec | 100 % | 25 to 200 % | Scales the hat tail length; 100% keeps the starting length. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### CHIP

File: [`Gen_Drum_3_Chip.ptfx`](Generators/Drum/Gen_Drum_3_Chip.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_3_Chip/Demo-1.wav) — ChipVector:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_3_Chip/Demo-2.wav) — ArcadeFracture:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.
- **[Demo 3](Audio/Drum/Gen_Drum_3_Chip/Demo-3.wav) — ArcadeExtras:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 0 ms release.

For game-inspired beats and crunchy percussion. Pulse and triangle tones, small wave tables and clocked noise follow short pitch and volume programs.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Toms8, Metal4, Extra8 | Chooses the kit layout; the number in its name is the slice count. |
| BD Type | Wave | Wave, Triangle, Pulse, Noise | Chooses the kick's chip source. |
| SD Type | Arcade | Arcade, Rise, NES, Metal | Chooses the snare's short sound program. |
| Noise | GB Long | NES Long, NES Short, GB Long, GB Short | Chooses the NES or Game Boy noise-register style. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |
| Sweep | 0 ofs | -100 to 100 ofs | Adjusts pitch movement around the starting program. |
| Snap | 0 ofs | -100 to 100 ofs | Changes the snare/clap attack and noisy snap. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Clock | 0 ofs | -100 to 100 ofs | Adjusts the chip noise clock. |
| Edge | 0 ofs | -100 to 100 ofs | Changes the sharpness and digital edge. |
| Resync | 0 % | 0 to 100 % | Adds repeatable noise-register resets. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### FM

File: [`Gen_Drum_4_FM.ptfx`](Generators/Drum/Gen_Drum_4_FM.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_4_FM/Demo-1.wav) — FMImpact:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_4_FM/Demo-2.wav) — FMMetal:** PTI preview: Beat Slice maps 4 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_4_FM/Demo-3.wav) — CeramicRitual:** PTI preview: Beat Slice maps 4 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 50 ms release.

For deep kicks, metallic percussion and digital kits. Oscillators modulate one another with different pitch ratios and fading envelopes. Each drum uses an appropriate FM arrangement.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Toms8, Metal4, Extra8 | Chooses the kit layout; the number in its name is the slice count. |
| Style | Classic | Classic, DeepTech, Industrial, Electro, Minimal, Metallic, Glitch, Soft, Hard, Experiment | Chooses a starting character for the whole kit. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Punch | 0 ofs | -100 to 100 ofs | Changes the kick's initial pitch movement and impact. |
| FM | 0 ofs | -100 to 100 ofs | Changes modulation depth for more or less metallic colour. |
| Snap | 0 ofs | -100 to 100 ofs | Changes the snare/clap attack and noisy snap. |
| Metal | 0 ofs | -100 to 100 ofs | Changes the metallic colour of hats and percussion. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Hat Col | 0 ofs | -100 to 100 ofs | Changes the hat's FM colour. |
| Hat Dec | 100 % | 25 to 200 % | Scales the hat tail length; 100% keeps the starting length. |
| BD Dec | 100 % | 25 to 200 % | Changes the bass drum tail length. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### PHASE

File: [`Gen_Drum_5_Phase.ptfx`](Generators/Drum/Gen_Drum_5_Phase.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_5_Phase/Demo-1.wav) — PhaseChrome:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_5_Phase/Demo-2.wav) — PhaseClatter:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_5_Phase/Demo-3.wav) — PhaseStones:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 50 ms release.

For synthetic drums with a sharp, unusual edge. Phase distortion changes the shape of each oscillator over the hit, with noise and drive adding texture.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Toms8, Metal4, Extra8 | Chooses the kit layout; the number in its name is the slice count. |
| Style | Classic | Classic, Electro, Synthwave, Industrial, Metallic, Lo-Fi | Chooses a starting character for the whole kit. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Warp | 0 ofs | -100 to 100 ofs | Changes the amount of phase distortion. |
| Sweep | 0 ofs | -100 to 100 ofs | Changes how the phase shape moves during each hit. |
| Noise | 0 ofs | -100 to 100 ofs | Changes the added noise component. |
| Drive | 0 dB | 0 to 24 dB; step 0.1 | Adds saturation and a rougher edge. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Clap | 0 ofs | -100 to 100 ofs | Changes clap articulation. |
| Hattone | 0 ofs | -100 to 100 ofs | Changes hat brightness and colour. |
| Metal | 0 ofs | -100 to 100 ofs | Changes the metallic colour of hats and percussion. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### SIX

File: [`Gen_Drum_6_Six.ptfx`](Generators/Drum/Gen_Drum_6_Six.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_6_Six/Demo-1.wav) — SixMachine:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_6_Six/Demo-2.wav) — SilverSix:** PTI preview: Beat Slice maps 4 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_6_Six/Demo-3.wav) — SixFurnace:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.

For compact, lively analog-style kits. Damped ringing tones form the bodies, with filtered noise and metallic oscillators for the sharper sounds. MetalAcc6 and FullAcc8 include an accented snare.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Toms6, MetalAcc6, FullAcc8 | Chooses the kit layout; the number in its name is the slice count. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |
| Metal | 0 | -100 to 100 | Changes the metallic colour of hats and percussion. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Punch | 28 % | 0 to 100 % | Changes the kick's initial pitch movement and impact. |
| Snap | 51 % | 0 to 100 % | Changes the snare/clap attack and noisy snap. |
| Drive | 0 dB | 0 to 6.0206 dB; step 0.1 | Adds saturation and a rougher edge. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### SEVEN

File: [`Gen_Drum_7_Seven.ptfx`](Generators/Drum/Gen_Drum_7_Seven.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_7_Seven/Demo-1.wav) — SevenPunch:** PTI preview: Beat Slice maps 4 generated hits to separate notes for a playable kit.
- **[Demo 2](Audio/Drum/Gen_Drum_7_Seven/Demo-2.wav) — SevenCutups:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.
- **[Demo 3](Audio/Drum/Gen_Drum_7_Seven/Demo-3.wav) — SevenDust:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 5 ms release.

For punchy PCM drum-machine sounds. It plays embedded drum samples, then changes their clock rate, envelopes, tone and bit resolution.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Ride8 | Chooses the kit layout; the number in its name is the slice count. |
| Clock | 100 % | 25 to 200 % | PCM playback speed; 100% is the normal clock. |
| Decay | 100 % | 25 to 200 % | Scales drum envelopes around their normal length. |
| Tone | 0 | -100 to 100 | Changes brightness and the selected model's tone colour. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Tail | 0 st | -12 to 0 st | Downward pitch change in the sample tail. |
| Hat Dec | 100 % | 25 to 200 % | Scales the hat tail length; 100% keeps the starting length. |
| Bit Cut | 0 bit | 0 to 4 bit | Number of low bits removed for a rougher sound. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### EIGHT

File: [`Gen_Drum_8_Eight.ptfx`](Generators/Drum/Gen_Drum_8_Eight.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_8_Eight/Demo-1.wav) — DeepEight:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_8_Eight/Demo-2.wav) — ChicagoEight:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_8_Eight/Demo-3.wav) — EightPressure:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.

For round bass drums, snappy snares and sizzling analog-style percussion. Ringing tone models, filtered noise and metallic pulse mixtures build the kit.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Classic8 | Basic4, Clap4, Basic6, Toms6, Basic8, Classic8, Congas8, Metal8 | Chooses the kit layout; the number in its name is the slice count. |
| BD Tune | 54 Hz | 32 to 126 Hz | Bass drum body frequency. |
| BD Dec | 65 % | 0 to 100 % | Changes the bass drum tail length. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Attack | 28 % | 0 to 100 % | Changes the bass drum attack and impact. |
| Snap | 71 % | 0 to 100 % | Changes the snare/clap attack and noisy snap. |
| Metal | 0 | -100 to 100 | Changes the metallic colour of hats and percussion. |
| Drive | 0 dB | 0 to 22.278867 dB; step 0.1 | Adds saturation and a rougher edge. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### NINE

File: [`Gen_Drum_9_Nine.ptfx`](Generators/Drum/Gen_Drum_9_Nine.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_9_Nine/Demo-1.wav) — ClassicNine:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_9_Nine/Demo-2.wav) — WarehouseNine:** PTI preview: Beat Slice maps 6 generated hits to separate notes for a playable kit.
- **[Demo 3](Audio/Drum/Gen_Drum_9_Nine/Demo-3.wav) — NineRazor:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.

For punchy dance kits. It combines synthesized drum bodies and noise with embedded PCM hats and cymbals. The metal tuning can be changed separately.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Clap4, Basic6, Toms6, Basic8, Classic8, Toms8, Metal4 | Chooses the kit layout; the number in its name is the slice count. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Snap | 67 % | 0 to 100 % | Changes the snare/clap attack and noisy snap. |
| Punch | 50 % | 0 to 100 % | Changes the kick's initial pitch movement and impact. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |
| BD Dec | 100 % | 25 to 200 % | Changes the bass drum tail length. |
| Me Tune | 0 st | -12 to 12 st | Tunes PCM hats and cymbals separately. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


### WAVE

File: [`Gen_Drum_10_Wave.ptfx`](Generators/Drum/Gen_Drum_10_Wave.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ ☕ (5/5)** — provisional allowance: about 1–3 minutes or longer; see the [coffee guide](#generation-time-the-coffee-guide). Renders a complete chain of drum voices; longer slots increase the work.

- **[Demo 1](Audio/Drum/Gen_Drum_10_Wave/Demo-1.wav) — DigitalEdge:** Source audition: no finished PTI processing is demonstrated. A Beat Slice PTI can map the generated drum slots to separate notes so the kit can be sequenced hit by hit.
- **[Demo 2](Audio/Drum/Gen_Drum_10_Wave/Demo-2.wav) — WaveRelics:** PTI preview: Beat Slice maps 4 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 50 ms release.
- **[Demo 3](Audio/Drum/Gen_Drum_10_Wave/Demo-3.wav) — CrushedObjects:** PTI preview: Beat Slice maps 8 generated hits to separate notes for a playable kit; the volume envelope keeps the attack immediate and sets a 30 ms release.

For flexible digital percussion. Changing wave shapes, folding, noise and resolution reduction build a kit that can range from clean to crushed.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Kit | Basic4 | Basic4, Basic6, Classic8, Toms8, Metal4, Extra8 | Chooses the kit layout; the number in its name is the slice count. |
| Style | Digital | Digital, Electro, Metal, Crushed | Chooses a starting character for the whole kit. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 % | 0 to 100 % | Sets how long the sound takes to fade. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Shape | 0 ofs | -100 to 100 ofs | Reshapes the waveform. |
| Skew | 0 ofs | -100 to 100 ofs | Makes the waveform less symmetrical. |
| Fold | 0 ofs | -100 to 100 ofs | Folds the wave back on itself for extra harmonics. |
| Crush | 0 ofs | -100 to 100 ofs | Adds coarse digital texture. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Clap | 0 ofs | -100 to 100 ofs | Changes clap shaping. |
| Hat Mix | 0 ofs | -100 to 100 ofs | Changes the balance of noise and tonal parts in the hats. |
| Metal | 0 ofs | -100 to 100 ofs | Changes the metallic colour of hats and percussion. |
| Balance | 0 | -100 to 100 | Negative values favour the kick; positive values favour the other hits. |


## Perc

[KICK](#kick) · [SNARE](#snare) · [CLAP](#clap) · [HAT](#hat) · [TOM](#tom) · [CONGA](#conga) · [RIM](#rim) · [CLAVES](#claves) · [COWBELL](#cowbell) · [BELL](#bell) · [CYMBAL](#cymbal) · [CRASH](#crash) · [RIDE](#ride) · [MARACAS](#maracas) · [ZAP](#zap)

These make one hit at a time, ready for normal one-shot sample playback. There is no kit to slice. Choose Model first, then adjust the sound. A PCM model starts from embedded sampled audio; its recording limits how far you can extend the tail. Decay shapes a fade and is not always the exact output-file length.


### KICK

File: [`Gen_Perc_01_Kick.ptfx`](Generators/Percussion/Gen_Perc_01_Kick.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_01_Kick/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_01_Kick/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_01_Kick/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For designing a single bass drum. Choose a sine-based, digital, chip, FM, phase, PCM or wave-based model, then shape the body, click and falling pitch.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | BASE | BASE, TONE Digi, CHIP Wave, FM, PHASE, SEVEN PCM, WAVE | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 350 ms | 40 to 1500 ms; step 10 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 30 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 35 % | 0 to 100 % | Moves from a stronger body toward more click. |
| Tone | 50 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| P Drop | 50 % | 0 to 100 % | Strength of the downward pitch movement. |
| Drive | 0 dB | 0 to 24 dB | Adds saturation and a rougher edge. |


### SNARE

File: [`Gen_Perc_02_Snare.ptfx`](Generators/Percussion/Gen_Perc_02_Snare.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_02_Snare/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_02_Snare/Demo-2.wav) — Model 5, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_02_Snare/Demo-3.wav) — Model 10, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For one snare with control over its body and noisy wires. Models use different combinations of oscillators, noise, FM, chip programs or PCM playback.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Tone DAC, ChipArcade, Chip NES, FM, Phase, Six, Seven PCM, Eight, Nine, Wave | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 180 ms | 40 to 600 ms | Sets how long the sound takes to fade. |
| Attack | 0.25 ms | 0.25 to 30 ms; step 0.25 | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 55 % | 0 to 100 % | Moves from tonal body toward noisy or metallic wires. |
| Tone | 50 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| WireDec | 100 % | 25 to 250 % | Length of the wire/noise tail relative to the body. |
| BodyShp | 50 % | 0 to 100 % | Changes body harmonics, waveform or PCM frequency split. |


### CLAP

File: [`Gen_Perc_03_Clap.ptfx`](Generators/Percussion/Gen_Perc_03_Clap.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_03_Clap/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_03_Clap/Demo-2.wav) — Model 4, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_03_Clap/Demo-3.wav) — Model 7, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For handclap-style hits and burst effects. Several short bursts lead into a tail. Different models use filtered noise, chip noise, FM, phase shaping or PCM layers.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | BaseNine | BaseNine, ToneDAC, ChipGB, FMChain, Phase, SevenPCM, Eight, Wave | Chooses the sound-making method. |
| Tune | 0 st | -12 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 200 ms | 40 to 600 ms | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 12 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 % | -100 to 100 % | Negative favours the bursts; positive favours the tail. |
| Tone | 50 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| Spacing | 11 ms | 5 to 30 ms | Time between the short clap bursts. |
| Bursts | 3 | 2 to 6 | Number of short bursts in the clap. |


### HAT

File: [`Gen_Perc_04_Hat.ptfx`](Generators/Percussion/Gen_Perc_04_Hat.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_04_Hat/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_04_Hat/Demo-2.wav) — Model 4, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_04_Hat/Demo-3.wav) — Model 9, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For short closed hats or longer open-hat sounds. It blends noisy and metallic parts, or shapes PCM hat material, with separate controls for the metallic tail.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Tone DAC, Chip, FM, Phase, Six, Seven PCM, Eight, Nine PCM, Wave | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 150 ms | 20 to 1200 ms | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 50 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 65 %met | 0 to 100 %met | Moves from noise toward the metallic component. |
| Tone | 60 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| Met Dec | 100 % | 25 to 200 % | Length of the metallic tail relative to the main decay. |
| Met Rat | 100 % | 50 to 200 % | Changes metallic tuning relationships or the PCM metal treatment. |


### TOM

File: [`Gen_Perc_05_Tom.ptfx`](Generators/Percussion/Gen_Perc_05_Tom.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_05_Tom/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_05_Tom/Demo-2.wav) — Model 4, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_05_Tom/Demo-3.wav) — Model 7, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For tuned fills and rounded percussion. Different ringing, digital and PCM models make a drum body with a controllable pitch bend and resonance.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Chip, FM, Phase, Six, Seven PCM, Nine, Wave | Chooses the sound-making method. |
| Tune | 0 st | -24 to 24 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 400 ms | 60 to 1600 ms; step 10 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 80 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 % | -100 to 100 % | Negative favours the body; positive favours the strike. |
| Tone | 50 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| P Bend | 5 st | -12 to 24 st | Sets the pitch bend at the start of the hit. |
| Reson | 50 % | 0 to 100 % | Changes the body's resonant colour. |


### CONGA

File: [`Gen_Perc_06_Conga.ptfx`](Generators/Percussion/Gen_Perc_06_Conga.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_06_Conga/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_06_Conga/Demo-2.wav) — Model 0, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_06_Conga/Demo-3.wav) — Model 1, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For rounded hand-drum-style hits. Two related tone models make a body and strike, with a short pitch bend and adjustable body colour.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Eight | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 220 ms | 40 to 800 ms | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 30 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 % | -100 to 100 % | Negative favours the body; positive favours the slap. |
| Tone | 65 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| P Bend | 3 st | -12 to 24 st | Sets the pitch bend at the start of the hit. |
| Body | 50 % | 0 to 100 % | Changes the body's tone and upper resonance. |


### RIM

File: [`Gen_Perc_07_Rim.ptfx`](Generators/Percussion/Gen_Perc_07_Rim.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_07_Rim/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_07_Rim/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_07_Rim/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For tight rimshots, clicks and ringing stick sounds. Different models combine a short strike with a ringing body. Ring controls shape the second part; the PCM model adds a resonator to its recorded hit.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Modal 1-8-9 | Modal 1-8-9, Tone Hybrid, Chip Program, FM Pair, Phase Double, Seven PCM, Wave Impact | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 45 ms | 10 to 200 ms | Sets how long the sound takes to fade. |
| Attack | 0.25 ms | 0.25 to 20 ms; step 0.25 | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 50 % | 0 to 100 % | Moves from click/strike toward ring/body. |
| Tone | 65 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| RingDec | 100 % | 25 to 300 % | Ring decay relative to the main Decay setting. |
| RingRat | 100 % | 50 to 200 % | Scales the ring tuning, phase harmonic or added PCM resonance. |


### CLAVES

File: [`Gen_Perc_08_Claves.ptfx`](Generators/Percussion/Gen_Perc_08_Claves.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_08_Claves/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_08_Claves/Demo-2.wav) — Model 2, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_08_Claves/Demo-3.wav) — Model 4, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For short wooden clicks and pitched accents. Tonal and chip-style models make a brief strike with a small ringing body. Hard changes the attack character.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Tone, Chip, Eight, Wave | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 60 ms | 10 to 400 ms | Sets how long the sound takes to fade. |
| Attack | 0 ms | 0 to 20 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 % | -100 to 100 % | Negative favours the body; positive favours the strike. |
| Tone | 65 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| P Bend | 0 st | -12 to 12 st | Sets the pitch bend at the start of the hit. |
| Hard | 40 % | 0 to 100 % | Hardness and brightness of the strike. |


### COWBELL

File: [`Gen_Perc_09_Cowbell.ptfx`](Generators/Percussion/Gen_Perc_09_Cowbell.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_09_Cowbell/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_09_Cowbell/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_09_Cowbell/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For clanging rhythmic accents. Paired tones or PCM bands create low and high components. Their balance, tuning relationship and damping set the clang.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | BASE | BASE, TONE DAC, CHIP, PHASE, SEVEN PCM, EIGHT, WAVE | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 220 ms | 40 to 1000 ms | Sets how long the sound takes to fade. |
| Attack | 0.5 ms | 0.25 to 40 ms; step 0.25 | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 0 % | -100 to 100 % | Negative favours the low component; positive favours the high one. |
| Tone | 0 % | -100 to 100 % | Changes brightness and the selected model's tone colour. |
| DmpTilt | 0 % | -100 to 100 % | Changes how quickly the upper part fades. Positive values shorten its tail. |
| Ratio | 1 x | 0.75 to 2 x; step 0.01 | Changes the relationship of the paired tones or PCM processing. |


### BELL

File: [`Gen_Perc_10_Bell.ptfx`](Generators/Percussion/Gen_Perc_10_Bell.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_10_Bell/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_10_Bell/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_10_Bell/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For ringing bell-like accents. Paired tones, digital shaping or processed PCM produce a strike and a longer body. Inharm changes how closely the upper tones relate to the main pitch.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Tone DAC, Chip, Phase, Seven PCM, Eight, Wave Ring | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 0.5 s | 0.08 to 4 s; step 0.01 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0.25 to 100 ms; step 0.25 | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 50 % | 0 to 100 % | Moves from the strike toward the ringing body. |
| Tone | 60 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| DmpTilt | 0 % | -100 to 100 % | Changes how quickly the upper part fades. Positive values shorten its tail. |
| Inharm | 50 % | 0 to 100 % | Changes upper-tone ratios; the PCM model uses ring modulation. |


### CYMBAL

File: [`Gen_Perc_11_Cymbal.ptfx`](Generators/Percussion/Gen_Perc_11_Cymbal.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_11_Cymbal/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_11_Cymbal/Demo-2.wav) — Model 4, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_11_Cymbal/Demo-3.wav) — Model 8, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For metallic hits and noisy washes. Oscillator, noise, FM, chip and PCM models offer different kinds of metal, with density and damping controls.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Eight | Tone, Chip, FM, Phase, Six, Seven PCM, Eight, Nine PCM, Wave | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 1200 ms | 150 to 4000 ms; step 10 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 100 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 70 %met | 0 to 100 %met | Moves from noisy wash toward metal. |
| Tone | 65 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| DmpTilt | 0 % | -100 to 100 % | Changes how quickly the upper part fades. Positive values shorten its tail. |
| Density | 60 % | 0 to 100 % | Changes the density of the metallic texture. |


### CRASH

File: [`Gen_Perc_12_Crash.ptfx`](Generators/Percussion/Gen_Perc_12_Crash.ptfx)

**Generation speed: ☕ ☕ ☕ (3/5)** — provisional allowance: about 15–30 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_12_Crash/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_12_Crash/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_12_Crash/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For impact accents that open into a wash. It uses synthetic, chip or PCM metal sources. Bloom lets the wash rise and last longer; Spread changes the sound within a mono sample.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Six | Six, Eight, Seven, Nine, Chip, FM, Phase | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 0.45 s | 0.15 to 0.75 s; step 0.01 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 150 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 60 % | 0 to 100 % | Moves from the initial impact toward sustained wash. |
| Tone | 60 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| Bloom | 30 % | 0 to 100 % | Slows the wash rise and extends the tail. |
| Spread | 50 % | 0 to 100 % | Spreads tonal ratios or bends the PCM tail; this is not stereo width. |


### RIDE

File: [`Gen_Perc_13_Ride.ptfx`](Generators/Percussion/Gen_Perc_13_Ride.ptfx)

**Generation speed: ☕ ☕ ☕ ☕ (4/5)** — provisional allowance: about 30–60 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_13_Ride/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_13_Ride/Demo-2.wav) — Model 3, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_13_Ride/Demo-3.wav) — Model 6, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For a clear ping over a longer cymbal wash. Different tone, chip, FM, phase and PCM models provide the source. Balance and WashDec let the ping or wash lead.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Tone | Tone, Chip, FM, Phase, Seven PCM, Nine PCM, Wave | Chooses the sound-making method. |
| Tune | 0 st | -12 to 12 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 900 ms | 100 to 2500 ms; step 10 | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 100 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 50 %wash | 0 to 100 %wash | Moves from the bell/ping toward the wash. |
| Tone | 55 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| WashDec | 100 % | 25 to 200 % | Wash tail length relative to the main Decay setting. |
| BellRat | 1.483 x | 0.75 to 2.5 x; step 0.01 | Changes the bell's tuning relationship or PCM bell treatment. |


### MARACAS

File: [`Gen_Perc_14_Maracas.ptfx`](Generators/Percussion/Gen_Perc_14_Maracas.ptfx)

**Generation speed: ☕ (1/5)** — provisional allowance: under 5 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_14_Maracas/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_14_Maracas/Demo-2.wav) — Model 0, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_14_Maracas/Demo-3.wav) — Model 0, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For a single shaker gesture. The Eight model uses filtered noise with an initial hit and a group of small grains. Density and BurstTm control the rattle. Eight is intentionally the only model.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Eight | Eight | Chooses the sound-making method. |
| Tune | 0 st | -24 to 12 st | Moves the noise filter; this changes colour rather than a musical note. |
| Decay | 75 ms | 20 to 500 ms | Sets how long the sound takes to fade. |
| Attack | 1 ms | 0 to 40 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 35 % | 0 to 100 % | Moves from the initial hit toward the following grains. |
| Tone | 65 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| BurstTm | 25 ms | 5 to 120 ms | Time from the first to the last grain. |
| Density | 8 grain | 2 to 32 grain | Number of small grains in the gesture. |


### ZAP

File: [`Gen_Perc_15_Zap.ptfx`](Generators/Percussion/Gen_Perc_15_Zap.ptfx)

**Generation speed: ☕ ☕ (2/5)** — provisional allowance: about 5–15 seconds; see the [coffee guide](#generation-time-the-coffee-guide). One hit at a time; model choice and tail length change the workload.

- **[Demo 1](Audio/Percussion/Gen_Perc_15_Zap/Demo-1.wav) — Model 0, Tune 0 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 2](Audio/Percussion/Gen_Perc_15_Zap/Demo-2.wav) — Model 2, Tune -5 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.
- **[Demo 3](Audio/Percussion/Gen_Perc_15_Zap/Demo-3.wav) — Model 4, Tune 7 st:** Source audition: no PTI processing is added; the tone and decay are generated directly. A one-shot PTI can add filtering and a volume envelope, but those additions are not heard here.

For laser hits, disco tom effects and falling electronic blips. Sine, chip, FM, phase and wave-based models follow a strong downward pitch sweep.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Model | Base | Base, Chip, FM Laser, Phase, Wave FX | Chooses the sound-making method. |
| Tune | 0 st | -24 to 24 st | Moves the pitch up or down. For PCM models it changes playback speed too. |
| Decay | 220 ms | 30 to 1800 ms | Sets how long the sound takes to fade. |
| Attack | 0 ms | 0 to 100 ms | Sets how gradually the sound starts. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Balance | 50 % | 0 to 100 % | Balances the simpler body and the model's brighter effect component. |
| Tone | 50 % | 0 to 100 % | Changes brightness and the selected model's tone colour. |
| Sweep | 12 x | 1 to 24 x | Starting pitch multiplier for the falling sweep. |
| SwpTime | 120 ms | 5 to 300 ms | How quickly the pitch sweep falls. |


## Effects and converters

[HOLY TRINITY](#holy-trinity) · [DATA ROT](#data-rot) · [OBERHEIM DX](#oberheim-dx) · [FAIRLIGHT CMI IIx](#fairlight-cmi-iix) · [NES DCM](#nes-dcm) · [EMU EMULATOR II](#emu-emulator-ii) · [ENSONIQ MIRAGE](#ensoniq-mirage) · [AMIGA PAULA](#amiga-paula) · [EMU SP-1200](#emu-sp-1200) · [OKI MSM6295](#oki-msm6295) · [AKAI MPC60](#akai-mpc60) · [MEGA DRIVE DAC](#mega-drive-dac) · [GAME BOY WAVE](#game-boy-wave) · [SNES BRR](#snes-brr) · [PS1 SPU](#ps1-spu)

Load an existing sample before using these. The converters put the sound through a vintage-style conversion or playback path and return normal Tracker audio. The names describe the sound being explored; they are not a promise of a complete hardware emulation.


### HOLY TRINITY

File: [`_holy_trinity.ptfx`](Effects/_holy_trinity.ptfx)

For tidying a finished sample. Crop it first, then apply this effect: it removes the constant waveform offset (DC), adds a 1 ms fade-in and 3 ms fade-out, and normalizes the peak to full scale. There are no adjustable controls.

| Name | Values / range | What it does |
| --- | --- | --- |
| Automatic cleanup | No controls | Removes DC, fades the edges and normalizes the peak. |


### DATA ROT

File: [`Effect_DataRot.ptfx`](Effects/Effect_DataRot.ptfx)

For damaged digital textures. It adds controlled dropouts, clock damage, stutters and ghost fragments to an existing sample. Seed lets you repeat a particular pattern of damage.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Age | 20 % | 0 to 100 % | Overall amount of deterioration. |
| Chance | 50 % | 0 to 100 % | How often damage occurs. |
| DACDrop | 60 % | 0 to 100 % | Amount of DAC/bit-level damage. |
| Clock | 50 % | 0 to 100 % | Amount of clock instability. |

#### Page 2

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Stutter | 50 % | 0 to 100 % | Amount of repeated fragments. |
| Ghost | 40 % | 0 to 100 % | Amount of ghost fragments. |
| Loss | 60 % | 0 to 100 % | Removes fine waveform detail for a smeared, damaged sound. |
| Size | 30 ms | 2 to 120 ms | Length of the damaged fragments. |

#### Page 3

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| Mix | 100 % | 0 to 100 % | Blend of original and damaged audio; 100% is fully processed. |
| Seed | 1 | 1 to 9999 | Selects a repeatable noise or variation pattern. |


### OBERHEIM DX

File: [`z_Convert_01_OberheimDX_Comp8.ptfx`](Effects/z_Convert_01_OberheimDX_Comp8.ptfx)

For gritty early drum-sampler colour. It simulates a compressed 8-bit conversion path, with a sample clock and output tone filter.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| CLOCK | 24 kHz | 4 to 48 kHz | Conversion clock rate. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 5950 Hz | 500 to 12000 Hz; step 50 | Output tone or filter brightness. |
| PATH | Cymbal | Cymbal, Tom | Chooses the cymbal or tom conversion/filter path. |


### FAIRLIGHT CMI IIx

File: [`z_Convert_02_FairlightCMIIx_PCM8.ptfx`](Effects/z_Convert_02_FairlightCMIIx_PCM8.ptfx)

For early digital sampler texture. It reduces the sample rate and converts the sound through an 8-bit PCM-style path, with filtering and smoothing.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 30 kHz | 4 to 30 kHz | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 10 kHz | 1 to 14 kHz | Output tone or filter brightness. |
| SMOOTH | 100 % | 0 to 100 % | Softens the steps and rough edges of the converted sound. |


### NES DCM

File: [`z_Convert_03_NES_DCM.ptfx`](Effects/z_Convert_03_NES_DCM.ptfx)

For crunchy NES-style sample playback. It encodes and decodes the sound using small up/down level steps, with a choice of 16 hardware-style clock rates.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 15 | 0 to 15 | NES clock index: 0 is slowest, 15 is fastest; these are choices, not kHz. |
| GAIN | 0 dB | -18 to 12 dB | Input level into the conversion. Higher settings can add distortion. |
| TONE | 8000 Hz | 1000 to 12000 Hz; step 100 | Output tone or filter brightness. |
| SMOOTH | 20 % | 0 to 100 % | Softens the steps and rough edges of the converted sound. |


### EMU EMULATOR II

File: [`z_Convert_04_EmuEmulatorII_Comp8.ptfx`](Effects/z_Convert_04_EmuEmulatorII_Comp8.ptfx)

For warm, grainy sampler colour. It uses a compressed 8-bit conversion model with a resonant output filter.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 27.777 kHz | 8 to 27.777 kHz; step 0.1 | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -24 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| CUTOFF | 9000 Hz | 100 to 12000 Hz; step 100 | Low-pass filter cutoff. Lower values remove more high frequencies. |
| RESO | 0 % | 0 to 90 % | Emphasizes the frequencies around the filter cutoff. |


### ENSONIQ MIRAGE

File: [`z_Convert_05_EnsoniqMirage_PCM8.ptfx`](Effects/z_Convert_05_EnsoniqMirage_PCM8.ptfx)

For rough 8-bit sampler tones. It combines rate reduction and 8-bit PCM conversion with a resonant low-pass filter.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 30 kHz | 10 to 33 kHz | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| CUTOFF | 9000 Hz | 50 to 15000 Hz; step 50 | Low-pass filter cutoff. Lower values remove more high frequencies. |
| RESO | 15 % | 0 to 100 % | Emphasizes the frequencies around the filter cutoff. |


### AMIGA PAULA

File: [`z_Convert_06_Amiga_Paula.ptfx`](Effects/z_Convert_06_Amiga_Paula.ptfx)

For classic tracker-style sample colour. It models 8-bit playback, clock periods, stepped volume and Amiga-style output filters.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| PERIOD | 214 PAL | 124 to 856 PAL | PAL playback clock period. Larger values give a lower sampling rate. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| VOLUME | 64 | 0 to 64 | Hardware-style volume steps; zero is silent. |
| FILTER | A500 | Raw, A500, A500 LED | Chooses raw output, A500 filtering or the darker LED filter. |


### EMU SP-1200

File: [`z_Convert_07_EmuSP1200_PCM12.ptfx`](Effects/z_Convert_07_EmuSP1200_PCM12.ptfx)

For gritty drum and sample textures. It uses a 12-bit sampling path with a speed-related colour control and different output-filter voices.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| SPEED | 7 semi | 0 to 24 semi | Simulates fast sampling followed by slow playback for more grit; keeps the original pitch and duration. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| VOICE | 7-8 Raw | 1-2 Sweep, 3-4 Dark, 5-6 Bright, 7-8 Raw | Chooses the output-filter character. |
| TONE | 100 % | 50 to 150 % | Scales the selected filter's brightness. |


### OKI MSM6295

File: [`z_Convert_08_OKIMSM6295_ADPCM.ptfx`](Effects/z_Convert_08_OKIMSM6295_ADPCM.ptfx)

For arcade-style sampled sound. It encodes and decodes through a low-rate ADPCM model, which stores changes in level instead of full sample values.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 7.576k | 6.061k, 7.576k, 12.121k, 15.152k | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 6000 Hz | 500 to 7000 Hz; step 100 | Output tone or filter brightness. |
| SMOOTH | 25 % | 0 to 100 % | Softens the steps and rough edges of the converted sound. |


### AKAI MPC60

File: [`z_Convert_09_AkaiMPC60_Comp12.ptfx`](Effects/z_Convert_09_AkaiMPC60_Comp12.ptfx)

For textured drum-sampler colour. It combines a reduced sampling rate with a compressed 12-bit conversion curve and tone filtering.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 40 kHz | 8 to 40 kHz | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -24 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 18 kHz | 2 to 18 kHz | Output tone or filter brightness. |
| CURVE | 100 % | 0 to 100 % | Strength of the compressed conversion curve. |


### MEGA DRIVE DAC

File: [`z_Convert_10_MegaDrive_DAC.ptfx`](Effects/z_Convert_10_MegaDrive_DAC.ptfx)

For crunchy console sample playback. It uses a reduced-rate 8-bit path and adjustable DAC ladder distortion.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 14 kHz | 4 to 32 kHz | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| LADDER | 100 % | 0 to 100 % | Amount of DAC ladder nonlinearity and distortion. |
| TONE | 12000 Hz | 1000 to 20000 Hz; step 100 | Output tone or filter brightness. |


### GAME BOY WAVE

File: [`z_Convert_11_GameBoy_Wave.ptfx`](Effects/z_Convert_11_GameBoy_Wave.ptfx)

For turning a small piece of a sample into a game-style tone. It takes a chosen window, reduces it to a 32-step, 4-bit waveform and plays it at the selected note.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| START | 0 ms | 0 to 100 ms | Where the source window begins in the input sample. |
| WINDOW | 168 smp | 32 to 1024 smp | Number of input samples used to build the short waveform. |
| NOTE | 60 MIDI | 36 to 96 MIDI | MIDI note used to play the resulting waveform. |
| LEVEL | 1 NR32 | 0 to 3 NR32 | Game Boy output level: 0 = mute, 1 = full, 2 = half, 3 = quarter. |


### SNES BRR

File: [`z_Convert_12_SNES_BRR.ptfx`](Effects/z_Convert_12_SNES_BRR.ptfx)

For SNES-style sampled colour. It passes the audio through BRR block compression and decoding, with optional Gaussian playback smoothing.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 32 kHz | 8 to 32 kHz | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 12 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 12 kHz | 2 to 16 kHz | Output tone or filter brightness. |
| GAUSS | 100 % | 0 to 100 % | Amount of Gaussian playback smoothing. |


### PS1 SPU

File: [`z_Convert_13_PS1_SPU.ptfx`](Effects/z_Convert_13_PS1_SPU.ptfx)

For PlayStation-style sampled texture. It uses an ADPCM encode/decode path with rate reduction, tone filtering and playback smoothing.

#### Page 1

| Name | Default | Values / range | What it does |
| --- | --- | --- | --- |
| RATE | 22.05 kHz | 8 to 44.1 kHz; step 0.05 | Sampling or conversion rate. Lower rates give a rougher, narrower sound. |
| GAIN | 0 dB | -18 to 18 dB; step 0.5 | Input level into the conversion. Higher settings can add distortion. |
| TONE | 10 kHz | 1 to 20 kHz | Output tone or filter brightness. |
| SMOOTH | 100 % | 0 to 100 % | Softens the steps and rough edges of the converted sound. |


## Keep exploring

Start with the defaults, change one control, and listen to what moves. Save sounds you like, then try a different method on the same musical idea. A clean sine bass, a folded wavetable and an FM bass can take the same pattern in very different directions.

The tables above follow the included PTFX parameter ranges and defaults. More detailed design and source notes live in [the generator documentation](docs/Polyend%20OG%20Generators) and [the percussion documentation](docs/percussion). Some development notes describe older revisions, so use the tables here for this collection's current controls. Hardware testing and listening coverage vary by plugin; see those notes for recorded limitations.

Built by Aisjam, with thanks to the [Polyend Tracker CE community](https://github.com/polyend/tracker-ce) and the source projects credited in the individual implementations.


## Audio demos

Each generator has three WAV previews. InstrumentPack source auditions demonstrate generated material; PTI previews add the saved instrument settings described beside each link. These existing previews may use earlier versions of the named generator. Percussion, PHASE WT and SUNSOFT demos were rendered from the included binaries without PTI processing; PHASE WT previews add a wavetable scan and fades. Offline previews can differ from Tracker playback.
