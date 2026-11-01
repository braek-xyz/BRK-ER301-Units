# BRK Tapz: multi-tap echo

BRK Tapz is the TAPZ echo from the BRAEK plug-in LAZERS. Instead of one echo that repeats, it makes a **row of up to
32 separate echoes** (taps) after the sound. You choose how long the row is and how many echoes are in it, then bend
their spacing, tilt their levels, spread them across the stereo field and colour their tone. The results go from a
simple slapback, to rhythmic bouncing-ball patterns, to a dense smeared cloud.

- Effect, stereo in / out (also works in mono chains)
- Syncs to a clock, or runs in free time
- Freeze turns the echoes into a loop
- Longest echo: 8.9 seconds

New to the BRK units? Read [Getting started](getting-started.md) first: it explains the knobs, the gates, the clock
and why `mix` starts at 0.

## Quick start

1. Put BRK Tapz after a sound, for example a short drum or plucked sound from IN1.
2. Turn **`mix`** up to about 0.5. You now hear 8 echoes spread over half a bar at 120 BPM, bouncing left and right.
3. Change **`taps`** (try 3, then 16) and **`len`** (try 1/8, then 1bar) to hear the row get shorter, longer,
   sparser or denser.
4. Turn **`space`** slowly away from 0.5 and listen to the echoes bunch up at one end.
5. Press **`frz`** (its fire button) to loop what is in the echoes. Press again to let go.

## The controls

Controls appear in this order on screen.

| On screen | Range (default) | What it does |
|---|---|---|
| `mix` | 0 to 1 (0) | Balance of dry sound and echoes. 0 = dry only, 1 = echoes only. |
| `len` | note lengths or time (1/2) | **Length of the whole row of echoes**: the time from the sound to the last echo. Synced: 1/16 to 2 bars, shown by name. Free (`free` on): 20 ms to 3.5 s (0.5 = about 265 ms). |
| `taps` | 1 to 32 (8) | **How many echoes** are in the row. More taps over the same `len` = closer together. |
| `space` | 0 to 1 (0.50) | **Spacing** of the echoes inside the row. 0.5 = evenly spaced. Below 0.5 the gaps get shorter and shorter (the echoes speed up, like a bouncing ball). Above 0.5 the first echoes come close together and the gaps grow (the echoes slow down). |
| `slope` | -1 to 1 (0.30) | **Tilts the echo levels.** Positive = each echo quieter than the one before (a natural fade). 0 = all echoes equally loud. Negative = echoes get louder towards the end (a reverse swell). |
| `fdbk` | 0 to 1 (0.20) | **Feedback**: sends the last echo back into the start of the row, so the whole pattern repeats and fades. High values make long, building repeats. |
| `sprd` | 0 to 1 (0.60) | **Stereo spread**: how far the echoes move away from the centre. 0 = all in the middle. |
| `mode` | 0 to 4 (1) | **How `sprd` places the echoes** (see below). |
| `filt` | 0 to 1 (0.70) | **Tone of the echoes.** Lower = darker and softer, higher = brighter. The dry sound is not filtered. |
| `shuf` | 0 to 1 (0) | **Shuffle**: small random nudges to each echo's timing, for a looser, more human or more broken feel. |
| `frz` | toggle (off) | **Freeze**: keeps the echoes going round in a loop and stops new sound coming in. Press again to release. |
| `hold` | momentary | **Freeze only while held.** Good for quick stutters from a gate or by hand. |
| `free` | toggle (off) | Off = `len` follows the clock (note lengths). On = `len` is free time in milliseconds. |
| `clock` | gate input | Clock pulses, one per beat. No clock = 120 BPM. |
| `div` | 1 to 32 (1) | Clock divider: how many incoming pulses make one beat (4 for a 16th-note clock, 24 for 24 PPQN). |

### The five spread modes (`mode`)

| `mode` | Name | What you hear |
|---|---|---|
| 0 | CLASSIC | The original LAZERS spread: right, left, right, left... Every feedback pass starts on the right again, so it leans right. |
| 1 | PING-PONG | (default) A balanced left / right bounce. Each feedback pass is the mirror image of the one before. |
| 2 | BLOOM | The first echoes sit near the centre and each later one is further out: the sound opens up. |
| 3 | SWEEP | The echoes travel from left to right, and the next feedback pass travels back, like a pendulum. |
| 4 | SCATTER | Every echo lands at its own spot across the stereo field: wild, but equally loud left and right. |

## How the controls work together

- **`len` and `taps` set the rhythm.** With `space` at 0.5, the echoes divide `len` evenly: `len` 1/2 with
  `taps` 4 gives echoes on every 1/8 note; `taps` 8 gives every 1/16 note.
- **`space` turns an even rhythm into an accelerating or slowing one** (bouncing ball), and `shuf` roughens it.
- **`slope` and `fdbk` set how long it lasts.** A positive `slope` with low `fdbk` is a short decaying burst. A flat
  `slope` with high `fdbk` is a long repeating pattern.
- **Freeze and `mix`**: if you freeze while `mix` is at 0, `mix` jumps to 0.7 so you can hear the frozen echoes
  (the same as in LAZERS).

## Patch ideas

- **Rhythmic delay:** synced, `len` 1/2, `taps` 4, `space` 0.5, `slope` 0.5, `fdbk` 0.3, `mode` 1.
  Four echoes on 1/8 notes, bouncing left and right, following your clock.
- **Bouncing ball:** `taps` 16, `space` 0.15, `slope` 0.6, `fdbk` 0. Each hit becomes a speeding-up roll.
- **Reverse swell:** `taps` 12, `slope` -0.8, `fdbk` 0, `len` 1bar. The echoes rise into the next downbeat.
- **Echo cloud:** `taps` 32, `shuf` 0.7, `fdbk` 0.6, `filt` 0.4, `mode` 4. A soft, dense wash.
- **Freeze on the beat:** patch a gate from your sequencer into `hold` to freeze short sections in time with the music.
- **Moving length:** an LFO on `len` (with `free` on) makes the echoes glide and pitch-bend like a tape delay.

## CPU

About 8 % on the ER-301 in normal use. The heaviest setting is `taps` 32 while `len`, `space` or `shuf` are moving.
