---
name: aor-ki
description: >
  Design, specify, and fabricate PandaMia — a voice-first organic bamboo command baton —
  and compile the result into printable parts, a mode classifier, and a host listen-event
  map. Use when the user says PandaMia, aor-ki, organic remote, voice-first clicker,
  bamboo presentation baton, sheaf remote, or wants a 3D-print fabrication spec for a
  one-hand staff/keynote/teach device with 3–4 dials, 639 Hz haptic, conductive sheaf,
  and a DriveLock interlock. Emits SKILL-compatible specs, OpenSCAD params, print/cast
  split, JAX+Vercel classification routes, and a mode map (DRIVE|TEACH|KEYNOTE|FACTORY|STUDIO).
  Do not use for weapons, surveillance kits, medical-frequency claims, or driving-while-operating
  a laser.
---

# /aor-ki

Architecture / Organic Remote / Kinetic Interface.

PandaMia is a one-hand command baton with an internodal bamboo feel: talk to staff,
teach a room, paginate a deck, record a decision. Eyes can stay forward. It is not a
living-room clicker and it is not a Cybertruck steering-wheel toy.

Assume the locked envelope below. State the feel SKU in one line (`light` or `planted`)
and proceed. Never interrogate.

## Locked envelope (ideal case v2)

| Param | Value |
|---|---|
| Form | Internodal bamboo flute segment, cylinder |
| Envelope | Ø34 × 128 mm |
| Volume | ~116.2 cm³ |
| feel=light | 64–72 g assembled |
| feel=planted | 100–110 g assembled (macadamia-oil analog 0.91 g/cm³ as *feel budget*) |
| Default vibe | planted (one-hand company baton) |
| Default all-day keynote | light |

Macadamia-oil density (0.905–0.920 g/ml) is a **feel metaphor and planted-SKU mass budget**,
not a claim that the device is filled with oil.

## Modes (mutually exclusive laser/HID vs DRIVE)

| Mode | Voice | Dials | Laser / mouse-gesture | Notes |
|---|---|---|---|---|
| DRIVE | yes | D1 D2 D3 | HARD OFF | IMU + vehicle BT hardware interlock. Haptic only. No hot-mic without grip-section. |
| TEACH | yes | D2 paginate/scroll | off | Room voice, next-idea |
| KEYNOTE | yes | D2 slide gain | on, interlocked | Class 2 ≤1 mW 532 nm. Long-press + voice `point`. Listen-events → HID click |
| FACTORY | PTT sheaf-squeeze | D3 channel | off | Walkie-style staff line. No laser near eyes or vehicles |
| STUDIO | yes | D4 macro | off | On-device VAD + host AI transcription |

Wake: `Panda` or sheaf-squeeze PTT.
Listen-events: `next | back | scroll {up,down} | point | click | mark | record | page {name} | mode {name} | send {channel}`.

## Grooves (datum z=0 at nose / laser cap, +z toward tail)

- Thumb pad: z=106 mm (22 mm from tail), azimuth +18°, ellipse 18×12 mm, depth 3.5 mm, fillet R3.2
- Second-finger internodal recess: z=68 mm, 18×12 mm, depth 4.5 mm, fillet R3.2
- Drive no-look tick: z=86 mm, 8×6 mm, depth 1.8 mm, azimuth −22°
- Palm flat: z=112–128 mm, span 115°
- Helical organic sweep +12° over 40 mm so the hand finds the grooves without looking

## Dials (bamboo-node rings, 9 mm tall, 1.4 mm proud, 8 magnetic detents)

- D1 MODE z=16–25 — DRIVE / TEACH / KEYNOTE / FACTORY / STUDIO + 3 user slots
- D2 GAIN z=40–49 — pagination / scroll / brief-stack
- D3 CHANNEL z=88–97 — staff / room / factory / AI-transcribe
- D4 MACRO z=118–127 — programmable; default `capture decision`

## Radial stack (outside → in)

1. Bamboo-PLA / wood-fill skin 0.8 mm, internodal texture
2. Ag/Ni-graphite or Ag/CNT conductive silicone sheaf 1.4 mm, Shore A 30–40
3. Ferrite-loaded polymer film A 0.4 mm (magnetic insulation)
4. Acrylic dielectric 0.4 mm
5. Helmholtz 639 Hz cavity (annular) + 12 mm piezo / LRA
6. Ferrite-loaded polymer film B 0.4 mm (flux return)
7. Structural bamboo-PLA core 1.2 mm
8. Core electronics: BLE + USB-C, dual MEMS mics, IMU, Class 2 laser, 250–400 mAh LiPo, haptic
9. Silver-tipped acrylic cylinder caps, silicone-held, magnetically seated

## Sheaf — physical and mathematical

Treat the conductive wrap as both a sheath and a sheaf.

- **Stalks** — local conductive patches: thumb, second-finger, palm, each cap
- **Restriction maps** — Ag/CNT traces that agree on overlaps
- **Global section** — grip-identity + presence + channel. Device is live only when a global section exists (palm+thumb commute). Fail-closed otherwise. This is why it does not hot-mic in a pocket.
- **Double magnetic insulation** — two restriction layers that kill inconsistent local flux so mics/IMU/MCU see a flat section. They **contain and locally concentrate** flux at cap snap faces. They do **not** amplify ambient magnetism. Non-ferrous bulk is mandatory. NdFeB lives only in dial detents and cap seats, in ferrite cups.

Surface resistivity: grip pads 10²–10⁴ Ω/sq; remainder ESD 10⁶–10⁸ Ω/sq.

## 639 Hz (brand haptic, not therapy)

Open-pipe ¼-wave at 639 Hz is 134 mm — too long for the baton. Use Helmholtz:

- Preferred: V = 5.0 cm³, neck Ø 3.0 mm, L = 8.0 mm → ~632 Hz; trim neck ±0.3 mm to 639 Hz
- Always pair with a 12 mm piezo + LRA driven at 639 Hz on connect / mode change / confirm
- Do not claim healing, DNA, or medical effects. Solfeggio language stays poetic, off-spec.

## Print vs not-print

**FDM** (bamboo-PLA or Bambu PLA Wood, ρ 1.14–1.21 g/cm³, 0.4 mm hardened nozzle, 220–230 °C, bed 35–45 °C, 15–25% gyroid):
- Outer skin clamshell, core shell, dial collars, magnet pockets (0.2 mm interference), assembly jigs
- Local 0.6 mm skin thicken at grooves so the overmold, not the print ridges, meets skin

**Cast / overmold:** conductive silicone sheaf, dual ferrite-silicone films.
**Machine / cast:** acrylic caps + silver tip ring (foil 0.3 mm or sputter 0.15 mm).
**COTS:** Class 2 532 nm ≤1 mW module, dual MEMS mics + VPU, IMU, BLE SoC, LRA, 250–400 mAh LiPo, USB-C.

## Fabrication app (Colossus workload shape)

Hardware strategy → workload shape → serving model.

| Route | Job | Runtime |
|---|---|---|
| `/studio` | Bamboo-node form generator + groove solver | Next.js |
| `/slice` | Printability / overhang / mold-draft / magnet-pocket classifier | jax-js (`@jax-js/jax`) in-browser |
| `/intent` | Mode + listen-event router | Vercel AI Gateway decision model (~100 ms) on Fluid |
| `/hid` | Listen-event → HID mouse/keyboard / app actions | Host agent |
| `/aor-ki` | Skill export (this package) | static |

Voxel features are stalks. A printable assembly is a global section. If restrictions do not commute (unsupported overhang over a magnet pocket, sheaf draft colliding with a groove), fail closed and classify `reprint`.

## Safety non-negotiables

- Class 2 laser only. DRIVE interlock is hardware + firmware, not a forgettable software toggle.
- Do not specify, encourage, or UX-design laser, mouse-gesture, or text entry while driving. The Cybertruck line is vibe: one-hand, eyes-forward, voice + tactile. Real primary use is stage, factory floor, studio, passenger seat.
- 639 Hz is a haptic/audio brand cue, never a medical claim.
- Conductive sheaf is presence and identity, not a field weapon.
- Magnets stay internal; outer stack non-ferrous.
- No manufacturing instructions for explosives, weapons, or covert surveillance.

## Protocol

1. Lock feel SKU (`light` or `planted`) and mode set.
2. Emit envelope + groove + dial table + stack (do not invent new diameters).
3. Split print / cast / COTS. Flag any part that is not hobby-printable.
4. Compile listen-event map and DriveLock interlock.
5. If asked for an app, scaffold the five routes above. Do not deploy without explicit approval.
6. Package updates back into this skill. Compound: every new printable constraint becomes a `/slice` class.

## Completion gate

- [ ] Envelope Ø34 × 128 mm and a named feel SKU
- [ ] Five modes with DRIVE laser/HID hard-off
- [ ] Groove and dial tables with datums
- [ ] Honest magnetics (contain + concentrate, not amplify ambient B)
- [ ] 639 Hz Helmholtz + piezo, no healing claims
- [ ] Print/cast/COTS split
- [ ] Listen-event taxonomy
- [ ] Sheaf-as-sheaf presence rule (fail-closed without global section)
- [ ] Safety paragraph present
