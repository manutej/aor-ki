---
name: aor-ki
description: |
  Design and fabricate PandaMia-class organic voice-first command remotes,
  and compile them into printable architecture plus host listen-event maps.
  Use when the user mentions PandaMia, aor-ki, organic bamboo remote,
  voice-first presenter, company baton, sheaf, 639 Hz, conductive silicone
  remote, or a one-hand command bar for teaching, keynote, staff, or drive-safe voice.
version: 0.2.0
user-invokable: true
argument-hint: "[envelope | mode | part | classify]"
metadata:
  product: PandaMia
  expand: Architecture / Organic Remote / Kinetic Interface
---

# /aor-ki — Architecture / Organic Remote / Kinetic Interface

PandaMia is not a living-room clicker. It is a one-hand command baton:
voice-first staff talk, pagination, scroll, and programmable modes, with an
organic bamboo internodal body and a conductive sheaf. The north-star vibe
is *one hand on the company, eyes forward* — never a text-while-driving toy.

## When to use

- Spec or revise PandaMia geometry, stack, modes, or BOM
- Compile a printable split (FDM vs overmold vs COTS)
- Classify a design variant (feel=light|planted, mode, printability)
- Export host listen-event maps (HID + AI transcription)
- Package or update this skill itself

## Locked envelope (ideal case v2)

Treat these as defaults. Override only with an explicit feel or mode flag.

| Param | Default | Notes |
|---|---|---|
| Form | internodal bamboo flute segment | not a slab remote |
| Diameter | 34 mm | comfort band 30–40 mm |
| Length | 128 mm | command-baton, not pen |
| Envelope volume | 116.2 cm³ | pi r^2 L |
| Oil analog | 106 g | macadamia rho ~ 0.914 g/cm³; feel metaphor + dense-node budget |
| Assembled mass light | 64–72 g | feel=light |
| Assembled mass planted | 100–110 g | feel=planted; Elon-baton default |
| Grip | thumb pad + second-finger internodal recess | no printed icons |
| Dials | 4 internodal rings, 8 detents | no-look |

### Groove defaults (z = 0 at nose cap)

- Thumb cradle: z=106 mm (22 mm from tail), azimuth +18 deg, ellipse 18 x 12 mm, depth 3.5 mm, fillet R3.2
- Second-finger recess: z=68 mm (38 mm forward of thumb), 18 x 12 mm, depth 4.5 mm, fillet R3.2
- Drive no-look tick: z=86 mm, 8 x 6 mm, depth 1.8 mm, azimuth -22 deg
- Palm flat: z=112–128 mm, span ~115 deg
- Helical organic sweep +12 deg over 40 mm so grooves find the hand

### Dials

- D1 MODE at z=16–25 — DRIVE / TEACH / KEYNOTE / FACTORY / STUDIO (+ 3 user slots)
- D2 GAIN at z=40–49 — pagination / scroll / brief-stack density
- D3 CHANNEL at z=88–97 — staff / room / factory line / AI-transcribe
- D4 MACRO at z=118–127 — programmable; default capture-decision / summon-agent

## Sheaf stack (outside to inside)

1. Bamboo-fiber / wood-fill skin with internodal rings
2. Ag/Ni-graphite or Ag/CNT conductive silicone sheaf (grip + presence)
3. Dual ferrite-loaded polymer flux-return films + 0.4 mm acrylic dielectric
4. Helmholtz pocket + 12 mm piezo / LRA driven at 639 Hz
5. Core: BLE HID, optional 2.4 GHz dongle, dual MEMS + VPU, IMU, cell, laser module
6. Silver-tipped acrylic cylinder caps, silicone-held, magnetically seated

Outer touch surfaces stay non-ferrous. Magnets and ferrite live inside.

### Sheaf mathematics (why the skill is named this way)

Physical sheath AND mathematical sheaf:
- stalks = local conductive patches (thumb, index, palm, each cap)
- restriction maps = Ag/CNT traces that must agree on overlaps
- global section = grip-identity + presence + channel
- device is ON only when a global section exists (palm+thumb glue)
- double magnetic insulation = two restriction layers that kill inconsistent local flux so electronics see a flat section

JAX classification reads voxel features as stalks. A printable assembly is a global section. Fail-closed if restrictions do not commute.

## Physics honesty (do not violate)

- 639 Hz is not a body-cavity resonance. Wavelength in air is ~537 mm; quarter-wave is ~134 mm. Use a driven piezo/LRA plus Helmholtz pocket (V = 5.0 cm3, neck 3.0 x 8.0 mm, trim ±0.3 mm to 639). Brand cue + haptic confirm only. No medical or healing claims.
- Double magnetic insulation to amplify magnetism is two jobs, not one. Insulation contains stray flux around mics, IMU, and MCU. Amplification is local at cap snap faces via ferrite cups or simplified Halbach rotation. Ideal concentrators do not raise magnet figure-of-merit. There is no free-space field amplifier in silicone.
- Carbon-fiber filament is dissipative, not wiring. Silver or silver-coated traces carry signal.

## Modes

Mutual exclusion is a safety property, not a preference.

- DRIVE: voice + D1-D3 + 639 Hz haptic. Laser HARD OFF. HID mouse-gesture HARD OFF. IMU + vehicle Bluetooth + sheaf global-section. No hot-mic without palm+thumb.
- TEACH: pagination, next idea, room voice. Laser off by default.
- KEYNOTE: Class 2 laser interlocked by long-press + voice "point". Listen-event mouse move/click.
- FACTORY: sheaf-squeeze PTT on D3 staff channel. Laser off near vehicles.
- STUDIO: record + on-device VAD + host AI transcription.

Laser ceiling: Class 2, ≤1 mW, 532 nm green if used. Interlock is hardware plus firmware. DRIVE cannot be a forgotten software toggle.

## Voice taxonomy (listen-events)

Wake: "Panda" or sheaf-squeeze PTT.

next | back | scroll up | scroll down | point | click | mark | record | page {name} | mode {name} | send {channel} | capture decision | summon agent

Host maps events to HID and app actions. Clicks may also be cap-squeeze. Transcription is host-side. On-device does VAD and beamform only.

## Fabrication split

Print (FDM bamboo-PLA / PLA-Wood, 0.4 mm hardened nozzle):
outer skin clamshell, structural core, dial collars, cap jigs, magnet pockets.

Do not print:
conductive silicone sheaf, ferrite films, acrylic+silver caps, NdFeB detents, laser module, MEMS mics, cell, piezo/LRA.

Classifier lanes (JAX-style, Vercel-served):
print-orientation, overhang, support, multi-material assignment, sheaf mold draft, magnet-pocket interference, mode-safety, feel.

## Adversarial checks (run before shipping a variant)

1. Does DRIVE cut laser and HID at the firmware layer?
2. Are magnets at least 8 mm from MEMS capsules?
3. Is assembled mass inside the selected feel band?
4. Is 639 Hz a driven Helmholtz transducer, not a fake pipe?
5. Is the outer stack still non-ferrous?
6. Are groove edges filleted?
7. Did anyone write a healing-frequency claim? Delete it.
8. Did anyone spec text entry as a driving UX? Delete it.
9. Does sheaf presence require a global section (palm+thumb)?

## Output contract

When this skill runs, emit:

1. Envelope table (D, L, volume, feel, mass band)
2. Stack outside-in with print vs not-print flags
3. Groove and dial coordinates
4. Mode matrix with interlocks
5. Listen-event map
6. Classifier scores (printability, safety, organic-feel, mass)
7. OpenSCAD or CadQuery parameter block, not a hazardous how-to

Do not emit magnetizing recipes, laser-diode drive circuits beyond class and power limits, or chemical formulations for conductive compounds.
