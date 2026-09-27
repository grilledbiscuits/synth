# Fully Analog Synthesizer Passion Project

> This repository documents some of the work I have done starting in 2024 on
> this project.

I have tried to include as many schematics as possible. The schematics are
mainly just for documentation's sake, as it is rather difficult to simulate the
constantly-changing signals involved in these circuits. I haven't been able to
order a PCB for any of the modules designed here for cost-related issues but I
intend to keep working on this project to polish it to the best of my ability.

---

## Modules

Every module lives as its own sheet in the
[`synth-allmodules`](KiCAD/current-modules/synth-allmodules) KiCad project, with
the reference circuit it was designed from kept in
[`KiCAD/references`](KiCAD/references).

| Module | Based on | Reference |
| --- | --- | --- |
| ADSR | Kassutronics Precision ADSR (Eddy Bergman version) | [image](KiCAD/references/ADSR) |
| 8 Step Sequencer | [Eddy Bergman, 8 Step Sequencer v2.1](https://www.eddybergman.com/2019/12/synthesizer-build-part-8-8-step.html) | [image](KiCAD/references/8stepsequencer) |
| Bass | Thomas Henry, Bass++ | [image](KiCAD/references/bass) |
| LFO | Ken Stone, CGS58 Utility LFO | [image](KiCAD/references/LFO) |
| VCA | Thomas Henry, VCA-1 | [image](KiCAD/references/VCA) |
| VCF-1 | [Thomas Henry, VCF-1 State Variable Filter](https://www.eddybergman.com/2024/04/THVCF1statevariablefilter.html) | [image](KiCAD/references/VCF-1) |
| VCF-2 | [YuSynth, Steiner-Parker Diode Filter](https://www.eddybergman.com/2021/12/synthersizer-build-part-45-steiner.html) | [image](KiCAD/references/VCF-2) |
| VCO | Thomas Henry, X-4046 VCO | [image](KiCAD/references/VCO) |
| 808 Kick | [Juanito Moore, 808 Kick](https://www.eddybergman.com/2021/12/synthesizer-build-part-46-808-kick-for.html) | [image](KiCAD/references/808kick) |

## Repository Layout

```
KiCAD/
├── current-modules/
│   ├── synth-allmodules/   # main project, one sheet per module
│   └── 8stepsequencer/     # standalone sequencer project
├── references/             # reference schematics, one folder per module
├── Library/                # custom symbols and footprints
└── DEPRECATED/             # older designs, kept for reference
SPICE Models/
SLDWRKS (DEPRECATED)/
```

To open the schematics, load
`KiCAD/current-modules/synth-allmodules/synth-allmodules.kicad_pro` in KiCad 10.

---

## Core Concepts

This project is going to require us to expand our current level of
understanding of the following areas of electronic engineering:

- Soldering skills
- PCB design
- Analog Signals
- Schematics

## To-Do

- [x] Initialise a repo
- [x] Start up a README
- [ ] Update all schematics
- [ ] Start with CAD design of housings
- [ ] Add mute switches to the sequencer!
- [ ] Add an amplifier
- [ ] Plenty of other things, no doubt

## Possible Cool Features

These are just me spitballing crazy ideas. None of these really have anything
to do with the base project but it would be cool if we could look into these
somewhat:

- More LEDs for better visual feedback
- Some cheap screens to watch the signals
- Increased modularity and uniform housings
- More modules!
- Portable version???
