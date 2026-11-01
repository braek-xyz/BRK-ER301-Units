# BRK Lazers: percussion voice

BRK Lazers is the sound engine of the BRAEK plug-in LAZERS, without its effects. It is a **percussion and
sound-design voice with 64 built-in sounds** (called slots): metallic FM hits, ticks, clicks, impulses, digital
pings, sub thumps, glitches, grain clouds, plucked strings, laser sweeps, claps and more. Every trigger plays a hit.
You shape each hit with attack, decay, a tuned tail, tone, noise, FM, drive and crush, and up to 16 hits can ring at
the same time.

- Sound source, stereo out (in a mono chain you get the left and right mixed)
- Trigger input plus V/oct pitch
- 64 sounds x 9 tail modes
- A built-in output limiter keeps every peak at or below -1 dBFS

The echo (TAPZ) and repeat (REPEAT) effects of LAZERS are the separate units [BRK Tapz](brk-tapz.md) and
[BRK Repeats](brk-repeats.md). Put them after BRK Lazers for the full LAZERS sound.

New to the BRK units? Read [Getting started](getting-started.md) first: it explains the knobs and the gates.

## Quick start

1. Put BRK Lazers in an **empty** chain (for example OUT1).
2. Select **`trig`** and press its **fire** button: you hear a hit. To play it from a patch, put a gate input
   (G1-G4) or a clock or sequencer unit in `trig`'s modulation chain.
3. Turn **`slot`** to hear the 64 sounds.
4. Turn up **`tail`** and step through **`tmode`** to add a tuned ring after each hit.
5. Patch a pitch CV into **`V/oct`** to play it melodically.

## Important: controls are read at the trigger

Like the plug-in, BRK Lazers reads its sound controls **at the moment of each trigger**. Turning a knob changes
the **next** hit, not the one that is already ringing. So for knob changes to be heard, keep triggering.
This is also what makes CV so useful here: a sequencer or random source on `slot`, `pitch`, `dec` or `tone` gives
every hit a different sound.
Only `pan` and `width` move all the time, also during a hit.

## The controls

Controls appear in this order on screen.

| On screen | Range (default) | What it does |
|---|---|---|
| `trig` | gate input | **Plays a hit** on every rising edge. |
| `V/oct` | pitch CV (0 V) | **Pitch from CV**, 1 volt per octave, read at the trigger. 0 V = the pitch set with `pitch`. |
| `vel` | 0 to 1 (1) | **Velocity**: how hard the hit is. Lower = quieter. Patch an accent or random CV here for dynamics. |
| `slot` | 1 to 64 (1) | **Which of the 64 sounds** plays (see the list below). |
| `pitch` | -24 to +24 semitones (0) | **Tunes the hit** up or down, up to 2 octaves each way. |
| `att` | 0 to 1 (0.10) | **Attack**: fade-in at the start of the hit, 0.5 to 100 ms. Low = a hard click, high = a softer start. |
| `dec` | 0 to 1 (0.33) | **Decay**: how long the hit rings out, 10 ms to 10 s. |
| `tail` | 0 to 1 (0) | **Tail**: a resonant ring at the slot's pitch after the hit, 30 ms to 10 s. 0 = no tail. |
| `tmode` | 0 to 8 (0) | **Tail mode**: the character of the tail (see below). |
| `tone` | 0 to 1 (0.75) | **Brightness**: a low-pass filter on the hit. Lower = darker. |
| `noise` | 0 to 1 (0.20) | Mixes a **noise layer** into the hit. |
| `fm` | 0 to 1 (0.30) | **The slot's own modulation.** Every slot uses it differently to change its character, so try it on each one. |
| `ratio` | 0 to 1 (0.40) | **FM ratio**: pitch of the extra FM modulator, 0.25x to 8x the pitch of the hit. Only heard when `index` is above 0. |
| `index` | 0 to 1 (0) | **FM index**: depth of the extra FM. 0 = off. Higher = brighter and more metallic. |
| `res` | 0 to 1 (0.10) | **Resonance**: emphasis at the `tone` filter's cutoff. |
| `drive` | 0 to 1 (0.10) | **Saturation**, from warm to gritty. |
| `crush` | 0 to 1 (0) | **Bit reduction** for a lo-fi, digital edge. |
| `pan` | -1 to 1 (0) | **Places the sound** left (-1) or right (1). |
| `width` | 0 to 1 (0) | **Stereo width**. 0 = mono. |
| `level` | in dB (+6 dB) | **Output level** (the LAZERS output stage). The limiter keeps every peak at or below -1 dBFS, so you can push it without clipping. |
| `poly` | 1 to 16 (8) | **How many hits can ring at the same time.** The voices take turns, so a new hit cuts off the oldest one. 1 = each hit cuts the last one off (a tight, choked sound). Higher `poly` also makes each hit a little quieter, so overlapping hits do not get too loud. Lower = less CPU. |
| `rand` | toggle (off) | **Random slot**: every hit plays a random slot. Great with a steady clock in `trig`. |

### Tail modes (`tmode`)

| `tmode` | Name | What you hear |
|---|---|---|
| 0 | RING | Three soft sine partials at the slot's pitch (the original LAZERS tail). |
| 1 | METAL | Clangy, uneven overtones of a struck metal bar, with a slow beating shimmer. |
| 2 | BELL | Bell overtones: a low hum under a bright, slightly minor strike tone. |
| 3 | DRUM | Tom / timpani body with a short downward pitch glide. |
| 4 | BOOM | A deep sine an octave down that drops in pitch: an 808-style sub tail. |
| 5 | STRING | A plucked string tuned to the slot, also excited by the hit itself. |
| 6 | AIR | A breathy, tuned noise wash. |
| 7 | RESONATE | The hit itself rings through four tuned resonators, so every slot rings in its own colour. |
| 8 | AUTO | Picks METAL, BELL, DRUM, BOOM, STRING, AIR or RESONATE to suit each slot. |

The tail is only heard when `tail` is above 0. Turn `tail` up to make the ring longer.

### The 64 sounds (`slot`)

There are 16 kinds of sound, each in 4 versions. Slots 1-16 are the first version of each, 17-32 the second, and so
on.

| Sound | Version 1 | Version 2 | Version 3 | Version 4 |
|---|---|---|---|---|
| FM METAL | 1 | 17 | 33 | 49 |
| MODAL TICK | 2 | 18 | 34 | 50 |
| NOISE IMPULSE | 3 | 19 | 35 | 51 |
| DIGITAL PING | 4 | 20 | 36 | 52 |
| RING HIT | 5 | 21 | 37 | 53 |
| SUB THUMP | 6 | 22 | 38 | 54 |
| GLITCH | 7 | 23 | 39 | 55 |
| GRAIN CLOUD | 8 | 24 | 40 | 56 |
| UNSTABLE ORGANIC | 9 | 25 | 41 | 57 |
| METAL HAT | 10 | 26 | 42 | 58 |
| STRING PLUCK | 11 | 27 | 43 | 59 |
| WAVEFOLD ZAP | 12 | 28 | 44 | 60 |
| LASER SWEEP | 13 | 29 | 45 | 61 |
| BLOOP | 14 | 30 | 46 | 62 |
| CLAP BURST | 15 | 31 | 47 | 63 |
| NOISE THUD | 16 | 32 | 48 | 64 |

## Patch ideas

- **Random percussion:** a clock into `trig`, `rand` on, `dec` 0.25, `tail` 0.3, `tmode` 8 (AUTO). A new sound on
  every step.
- **Tuned metallic sequence:** a pitch sequence into `V/oct`, gates into `trig`, `slot` 1 (FM METAL), `index` 0.4,
  `tail` 0.5, `tmode` 2 (BELL).
- **808-style kick and sub:** `slot` 6 (SUB THUMP), `pitch` -12, `tail` 0.5, `tmode` 4 (BOOM), `drive` 0.3.
- **Plucked melody:** `slot` 11 (STRING PLUCK), `tail` 0.5, `tmode` 5 (STRING), pitch CV into `V/oct`.
- **Accents:** an envelope or a second sequencer lane into `vel`, and a random source into `tone` for hits that
  never repeat exactly.
- **Full LAZERS chain:** BRK Lazers, then BRK Repeats, then BRK Tapz in the same chain, all on the same clock.

## CPU

BRK Lazers uses almost no CPU when it is silent. Each ringing hit adds to the load, so CPU depends on how many hits
overlap:

- one hit at a time: about 20 %
- busy patterns with long decays: about 60 %
- `poly` 8 with long tails: about 68 %

To save CPU, lower `poly`, shorten `dec` and `tail`, and keep `noise` and `index` at 0 when you do not need them.
