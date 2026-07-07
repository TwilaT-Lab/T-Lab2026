---
layout: default
title: fNIRS Signal Optimization
parent: fNIRS
nav_order: 8
---
# fNIRS Signal Optimization

Run this **after** the cap is on the participant and the correct configuration is loaded in Aurora, **before** starting the recording.

## 1. Load the Configuration
1. Open Aurora, connect NIRx broadcast Wi-Fi, and click the device icon. If the device doesn't appear automatically, click **"Refresh list."**
> If the device is on but not auto-connecting, enter the password printed on the bottom of the NIRSport2 unit.
3. Click the configuration
4. Confirm the loaded montage matches the cap you just built.
> Avoid turning the NIRSport2 on right before recording. Turn it on ahead of time.

---

## 2. Run Signal Optimization
Start the optimization routine (▶ play button). This is an **iterative process** — fix, refresh, re-check, repeat.

### Key metrics (color-coded):

| Color | Meaning |
|---|---|
| 🟢 Green | Excellent |
| 🟡 Yellow | Acceptable |
| 🔴 Red | Critical — needs attention |
| ⚪ Grey/White | Lost / too low / saturated |

| Metric | What it means | Thresholds |
|---|---|---|
| **CV (Coefficient of Variation)** | Signal variability — high CV usually = poor scalp contact. **Start troubleshooting here first.** | Excellent < 2.5%, Acceptable 2.5–7.5%, Critical > 7.5% |
| **Signal Level** | Raw voltage at the detector. Low = poor contact (hair, cap fit) or hardware issue | Excellent > 3 mV, Acceptable 0.5–3 mV, Critical < 0.5 mV |
| **Dark Noise** | Detector sensitivity with sources off. High = ambient/IR light interference | Excellent 3–12 µV, Acceptable 12–20 µV, Critical < 3 or > 20 µV |
| **Source Brightness** | Auto-adjusted; no action needed if other metrics are fine | — |

> **Priority:** An acceptable/excellent **CV** outweighs a borderline signal level. It's fine to settle for "acceptable" rather than "excellent," but both should clear the acceptable threshold before recording.

- Keep the participant still for a few seconds during optimization for an accurate reading.
- Some devices support **continuous optimization** (loop icon next to stop) — **stop continuous mode before starting the actual recording.**

---

## 3. Troubleshooting Poor Signal

| Likely cause | Fix |
|---|---|
| Hair blocking optical contact | Part hair, turn optode tip, increase spring-top tension|
| Cap setup not optimal | Recheck cap size, stabilizers, cable tree routing, Velcro strap |
| Probe placement mismatch | Confirm physical stickers match grommet labels and the loaded montage |
| Inter-optode distance too long | Recheck distances in NIRSite (should be ≤ ~4 cm) |
| Environmental light interference | Use blackout cap|
| Skull thickness | Use higher spring-top tension|
| Optode bundle not fully secured / wrong order | Reseat bundle connectors; check Sources A/B, Detectors A/B ports |
| Broken optode | Run a static phantom test; swap in spare optode if confirmed faulty |

- Re-run optimization after each fix.
- Use **Refresh** for live feedback while making adjustments
— run the full optimization (▶) again once you're done adjusting.
> **A comprehensive guide of troubleshooting related to signal:** [Refer to this manual](https://nirx.sharefile.com/share/view/sef0f1bc2ebb4723a)

---

## 4. Visual / Physiological Check
Before moving to recording, preview the live signal:
- Look for a **clear heartbeat-frequency oscillation** (~0.8–2 Hz) in the raw trace.
- HbO variation should be noticeably larger than HbR, and the two should be loosely anti-correlated.
- Ask the participant to move slightly to check for motion-artefact spikes.

---

## 5. Before Proceeding to Recording
- [ ] All ROI channels ideally green
- [ ] Physical signal visible

Next: [fNIRS Recording](./fNIRS-Recording)
