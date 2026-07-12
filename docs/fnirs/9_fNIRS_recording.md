---
layout: default
title: fNIRS Recording
parent: fNIRS
nav_order: 9
---
# fNIRS Recording

## Before the Participant Arrives
1. Remember to fully charge the NIRSport2 device before recording.
2. Log into the NIRSport2 laptop and open **Network and Internet settings** → click on broadcast name to connect wirelessly. *(The device can also connect via USB cable.)*
![wifi_fNIRS]({{ '/docs/images/wifi_fNIRS.png' | relative_url }})

4. Turn on the NIRSport2: hold **Power** until it turns green.
   > Avoid powering on right before recording — early power-on can cause signal drift.
![power_on_fNIRS]({{ '/docs/images/power_on_fNIRS.png' | relative_url }})

5. Plug in sources, detectors, and the trigger cable into the NIRSport2.
[photo needed]
7. Open Aurora → Select the device.
   - No device showing? Click **"Refresh list."**
   - Device on but not auto-connecting? Enter the password printed on the bottom of the NIRSport2 unit.
![device_selection]({{ '/docs/images/device_selection.png' | relative_url }})
8. Click your study's configuration name. (Maybe need more in detailed instruction here)
[photo_needed]
---

## Participant Setup
1. Briefly introduce the fNIRS and experiment setup and have the participant sit comfortably
2. Place the populated cap (see [Participant Preparation](https://twilat-lab.github.io/T-Lab2026/docs/fnirs/6_head_measuring_and_cap_fitting.html) for full fitting steps)
3. Glasses off during cap placement, can be worn again afterward. Long hair down before placement.

---

## Calibration (Signal Optimization)
# Please conduct calibration after the cap is on the participant and the correct configuration is loaded in Aurora, before starting the recording.
1. Load the saved montage/configuration in Aurora.
2. Start signal optimization and iterate until channels read green/acceptable.
3. **Stop continuous/loop optimization mode before recording** (click the stop button next to the loop icon).
4. Confirm a clear heartbeat-frequency oscillation (~0.8–2 Hz) is visible in the raw trace.

Full troubleshooting reference: [fNIRS Signal Optimization](./fNIRS-Signal-Optimization)

---

## Starting the Recording
1. Enter recording mode (button shown in Aurora's main interface).
2. **Start** with the circle button; **Stop** with the stop button.
3. Record a few seconds of **baseline** before starting the stimulus script.
4. Start the PsychoPy/stimulus script so triggers begin streaming (see [PsychoPy Setup](./PsychoPy-Setup)).

---

## During Recording
- Monitor the live data and device connection status throughout.
- RAs can manually mark an incident with trigger **F1–F12**.
- **Watch for:** sudden loud sounds, optode contact disruption, large body movement — all drift sources.
- Record any bad channels as you notice them.
- Stop the recording only **after** the task has fully completed.

---

## After Recording
- Run **Offline Review** to check markers and signal quality before exporting to Satori.
- Back up the data.
- Record session notes — deviations, fussiness, technical issues, anything relevant to QC later.
