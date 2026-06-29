---
layout: default
title: Psychopy Setup
parent: fNIRS
nav_order: 6
---
# PsychoPy Setup

PsychoPy handles stimulus presentation and (in this lab) trigger delivery to Aurora. Triggers mark the onset/offset of each condition so Satori can tell conditions apart during analysis.

## Trigger Options

| Method | Description |
|---|---|
| Manual | F1–F12 keys, up to 12 distinct markers |
| Wired | Trigger cable + Cedrus C-POD |
| Wireless | Lab Streaming Layer (LSL) — **preferred method in this lab** |

---

## Wired Triggering (Trigger Cable + C-POD) — Code Setup

In PsychoPy, select the serial port and use a Code Component to send TTL pulses.

### Step 1 — Initialize Serial Connection
Add a **Code Component** to the start routine → **"Begin Experiment"** tab:

```python
import serial
port = serial.Serial('COM3')  # Modify 'COM3' to match your device port
```

### Step 2 — Set Up State Variables
In the trial routine where triggers are needed → Code Component → **"Begin Routine"** tab:

```python
stimulus_pulse_started = False
stimulus_pulse_ended = False
```

### Step 3 — Configure Frame-Synchronized Triggering
Same trial routine → **"Each Frame"** tab. Rename `stimulus` to match your actual visual/auditory component name:

```python
if stimulus.status == STARTED and not stimulus_pulse_started:
    win.callOnFlip(port.write, str.encode('1'))
    stimulus_pulse_start_time = globalClock.getTime()
    stimulus_pulse_started = True

if stimulus_pulse_started and not stimulus_pulse_ended:
    if globalClock.getTime() - stimulus_pulse_start_time >= 0.005:
        win.callOnFlip(port.write, str.encode('0'))
        stimulus_pulse_ended = True
```

### Step 4 — Terminate Hardware Connection
In the final routine → Code Component → **"End Experiment"** tab:

```python
port.close()
```

> **Hardware note:** The NIRSport2 trigger input accepts a TTL-level (0–5V) positive-edge pulse of at least 10 ms duration.

---

## Wireless Triggering via LSL (Preferred)

LSL synchronizes data and triggers over the same Wi-Fi/router network already used for the Aurora device connection.

- In Aurora's configuration, set the **Trigger in** stream name (default: `"Trigger"`).
- The stream name on the **PsychoPy side must match exactly** — a mismatch silently drops all triggers.
- Use Aurora's **Test Connection** button to confirm the stream is live before recording.

> **Recommended order:** Start Aurora first → record a few seconds of baseline → then start the PsychoPy script. Confirm the LSL stream name matches on both sides **every session**, not just the first time.

---

## General Reminders
- Manual triggers (F1–F12) are best used for logging unexpected events (motion, noise) — not as the primary way of marking experimental conditions.
- Make sure manually-used marker numbers aren't already assigned to an experimental condition.
- Trigger files are saved automatically: `*_lsl.tri` (LSL/manual) and `*.tri` (hardware) in the recording's data folder.
