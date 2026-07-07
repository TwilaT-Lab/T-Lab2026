---
layout: default
title: fNIRS Recording
parent: fNIRS
nav_order: 9
---
# fNIRS Recording

## Before the Participant Arrives
1. Log into the NIRSport2 laptop and plug the router into the outlet.
2. Open **Network and Internet settings** → click on your access point's broadcast name to connect wirelessly. *(The device can also connect via USB cable.)*
   
4. Turn on the NIRSport2: hold **Power** until it turns green.
   > Avoid powering on right before recording — early power-on can cause signal drift.
5. Plug in sources, detectors, and the trigger cable into the NIRSport2.
6. Open Aurora → Select the device.
   - No device showing? Click **"Refresh list."**
   - Device on but not auto-connecting? Enter the password printed on the bottom of the NIRSport2 unit.
7. Click your study's configuration name.
---

## Participant Setup
1. Briefly introduce the fNIRS and experiment setup; have the participant sit comfortably, minimizing body movement.
2. Place the populated cap (see [Participant Preparation](./Participant-Preparation) for full fitting steps):
   - Seam above the eyebrows, level
   - Cap tag (back of cap) pulled out
   - Fpz equidistant from Nz/AFz; Cz equidistant from Nz/Iz and LPA/RPA
3. Glasses off during cap placement, can be worn again afterward. Long hair down before placement.
4. Manage environmental light: dim room **or** blackout cloth/overcap over the cap, depending on what the participant tolerates.

---

## Calibration (Signal Optimization)
1. Load the saved montage/configuration in Aurora.
2. Start signal optimization and iterate until channels read green/acceptable.
3. Check the three key indicators:

| Indicator | Watch for |
|---|---|
| Signal Level | Low → adjust hair / optode contact |
| Dark Noise | High → poor optode contact or environmental light |
| CV | High → variance / unstable contact |

4. **Stop continuous/loop optimization mode before recording** (click the stop button next to the loop icon).
5. Confirm a clear heartbeat-frequency oscillation (~0.8–2 Hz) is visible in the raw trace.

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
- RAs can manually mark an incident with **F1–F12** (e.g. sudden loud sound, optode touched, large body movement). These can also be edited afterward in the `.tri` file if needed — but get it right live whenever possible.
- **Watch for:** sudden loud sounds, optode contact disruption, large body movement — all common drift sources.
- Record any bad channels as you notice them.
- Stop the recording only **after** the task has fully completed.

---

## After Recording
- Run **Offline Review** to check markers and signal quality before exporting to Satori.
- Back up the data.
- Record session notes — deviations, fussiness, technical issues, anything relevant to QC later.

Next: [fNIRS Hyperscanning](./fNIRS-Hyperscanning)
