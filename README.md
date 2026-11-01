# BRK units for the ER-301

Three free units for the [Orthogonal Devices ER-301](https://orthogonaldevices.com/er-301), by **BRAEK** (Victoria, Australia).
They bring parts of the BRAEK plug-in **LAZERS** to the ER-301.

| Unit | Version | What it is |
|---|---|---|
| **BRK Tapz** | 0.3.2 | Multi-tap echo: up to 32 echoes with spacing, slope, feedback, stereo spread modes, filter, shuffle and freeze. Syncs to a clock. |
| **BRK Repeats** | 0.2.2 | Beat repeater: slices and repeats what comes in, with random gaps and jumps (braek), speed / direction wobble (wonk), lo-fi damage and freeze. Syncs to a clock. |
| **BRK Lazers** | 0.2.3 | The LAZERS sound source without its effects: 64 sounds, tails with 9 tail modes, FM, drive, crush, up to 16 voices. A trigger plays a hit; V/oct for pitch. |

Every control can be patched from CV. BRK Tapz and BRK Repeats are stereo in / out (mono chains work too).
BRK Lazers is a sound source: put it in an empty chain.

## Download

Go to **[Releases](../../releases/latest)** and download the three `.pkg` files:
`brk_tapz-0.3.2.pkg`, `brk_repeat-0.2.2.pkg`, `lazers-0.2.3.pkg`.

## Install

1. Turn off the ER-301 and take out the **front** SD card.
2. On your computer, copy the `.pkg` files into the `ER-301/packages` folder on that card.
   If you have older versions of these units there, delete the old `.pkg` files.
3. Put the card back and turn the ER-301 on.
4. Open the ER-301 **Package Manager**, select each BRK package and install it.
5. **Restart the ER-301.** This matters: until you restart, an older version can stay loaded.
6. The units are in the unit list under the **BRAEK** category.

## Works with

Built for ER-301 firmware **v0.6.03 and later, including v0.7.x**.
Tested by BRAEK on firmware 0.7.0-stolemine 9.5.2.

## CPU

Rough figures from BRAEK's ER-301: BRK Tapz about 8 %, BRK Repeats about 16 %, BRK Lazers about 68 % at POLY 8 with a
long tail (fewer voices or a shorter tail use less).
Tip: on the ER-301, bypassing a unit does not stop it using CPU unless
*Settings > Units > "Does bypassing a unit also disable it?"* is set to **yes**.

## Controls

**BRK Tapz:** mix, len (echo length; note names when synced), taps (1-32), space, slope, fdbk, sprd,
mode (0 CLASSIC, 1 PING-PONG, 2 BLOOM, 3 SWEEP, 4 SCATTER), filt, shuf, frz, hold, free (off = synced), clock, div.

**BRK Repeats:** mix, time (cycle length; note names when synced), rpts (1-16), pos, braek, wonk, dmg, frz, hold,
free (off = synced), clock, div.

**BRK Lazers:** trig, V/oct, vel, slot (1-64), pitch, att, dec, tail, tmode (0 RING, 1 METAL, 2 BELL, 3 DRUM, 4 BOOM,
5 STRING, 6 AIR, 7 RESONATE, 8 AUTO), tone, noise, fm, ratio, index, res, drive, crush, pan, width, level,
poly (1-16), rand.

With no clock patched, Tapz and Repeats run at 120 BPM. `div` divides the incoming clock (24 = 24 PPQN).

## Terms

© BRAEK. Free to use, including in commercial music. Please share a link to this page rather than re-uploading the
files. No warranty: use at your own risk.

Questions or problems: open an [issue](../../issues).
