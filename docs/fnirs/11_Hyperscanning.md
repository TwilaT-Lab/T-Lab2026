---
layout: default
title: fNIRS Hyperscanning
parent: fNIRS
nav_order: 11
---
# fNIRS Hyperscanning

Hyperscanning records two participants (e.g. parent + child) simultaneously, with synchronized data and shared event markers, using Aurora's **Hyperscan** application.

## 1. Cap Preparation
Prepare and populate **two separate caps**:

| Cap | Average Size |
|---|---|
| Child | ~52 cm |
| Parent | ~56 cm |

See [Building the fNIRS Cap](./Building-the-fNIRS-Cap) and [Populating the fNIRS Cap](./Populating-the-fNIRS-Cap) for the build process — do this for both caps in advance.

---

## 2. "Small +" vs. "Big +"

| | **Small + ** (Add subject to *this* device) | **Big +** (Add Subject) |
|---|---|---|
| Meaning | Both participants share **one** physical NIRSport2 | Each participant has their **own separate** device |
| If one participant moves | **Both** must be recalibrated (shared device) | Only the **affected** participant needs recalibration |
| Configuration | Each participant can still use a different config | Each device/participant fully independent |

> **Before recording:** Confirm Device ID ↔ Subject assignment carefully — it's much easier to verify this upfront than to untangle it after the session.

---

## 3. Setting Up a Hyperscan Session
1. Configure the network/access point on **each device individually** first (SSID + password from the router; country = Singapore for this lab setting), then power-cycle each device.
2. Connect the laptop's Wi-Fi to the same router (use 2.4 GHz unless 5 GHz has been explicitly configured).
3. Open the **Hyperscan** application (installed automatically with Aurora).
4. Click **"+"** to create subject profiles, using clear suffix coding, e.g. `XXX_C` (child) / `XXX_P` (parent):
   - **Add Subject ("big +")** for the first participant: Subject Name (required), Device ID (required), Configuration (required); age/gender/contact info optional.
   - For a 2nd participant on the **same** device: use **"Add subject to this Device" ("small +")** — Device ID greys out, but Configuration can still differ.
   - For a 2nd participant on a **separate** device: use **"Add Subject" ("big +")** again with that device's own Device ID.
5. Press **Connect to Aurora** for each subject — status shows *Initialising…* then *Ready*.

---

## 4. Simultaneous Optimization
- Clicking **Play** in Hyperscan opens two side-by-side Aurora optimization windows.
- Manually adjust both caps until **all channels are green or acceptable (yellow)**.
- You can optimize all subjects together from the main dashboard, or individually from a subject's own toolbar.

---

## 5. Recording
- Once every subject shows *Ready*/optimized, start **Data Recording** — together (main dashboard) or individually.
- Recording may start at very slightly different times across subjects due to network/computer lag — **rely on shared triggers, not start times,** to synchronize datasets during analysis.
- **Primary triggering focus:** bring the parent's window to the absolute front of the desktop. All interactive event triggers should be targeted onto the **parent window** as the unified timeline anchor.
- It's recommended to send triggers (manual, TTL, or LSL) to **both** Aurora instances.

To end a session: stop each recording individually, then simply close the Hyperscan application — this remotely stops all Aurora activity across every connected device.

---

## 6. Paediatric / Parent–Child Considerations
- Use child-friendly explanations throughout setup; keep the environment calm.
- Minimize cable tugging and unnecessary seat/position changes once both participants are set up.
- Budget extra time for hair management if either participant has thick, curly, or long hair.
- For a participant wearing a hijab, arrange a female-only setup if needed, and allow re-covering after the cap is placed where it doesn't compromise signal quality.
- Document any major movement, fussiness, interruptions, or script deviations in session notes — valuable context during later QC/analysis.

---

## Quick Reference

| Problem | Likely Cause | Action |
|---|---|---|
| One participant moves mid-session | Motion/cap shift | **Same device (small +):** recalibrate both. **Different devices (big +):** recalibrate only the affected participant |
| Triggers missing on one side | LSL/wired mismatch | Re-check stream names on both Aurora instances and the stimulus script |
| Recording start times don't match | Normal network/computer lag | Use shared triggers, not start timestamps, to align data in analysis |
