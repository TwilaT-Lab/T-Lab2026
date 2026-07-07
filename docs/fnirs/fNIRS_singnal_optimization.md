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
3. If the device is on but not auto-connecting, enter the password printed on the bottom of the NIRSport2 unit.
4. Click the configuration name for your study → a red checkmark appears and a new window opens.
5. Confirm the loaded montage matches the cap you just built.

> Avoid turning the NIRSport2 on right before recording — early power-on can cause signal drift. Turn it on a bit ahead of time.

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
| **Source Brightness** | Auto-adjusted; informational only — no action needed if other metrics are fine | — |

> **Priority:** An acceptable/excellent **CV** outweighs a borderline signal level. It's fine to settle for "acceptable" rather than "excellent," but both should clear the acceptable threshold before recording.

- Keep the participant still for a few seconds during optimization for an accurate reading.
- Some devices support **continuous optimization** (loop icon next to stop) for real-time adjustment — **stop continuous mode before starting the actual recording.**

---

## 3. Troubleshooting Poor Signal

| Likely cause | Fix |
|---|---|
| 1. Hair blocking optical contact | Part hair, increase spring-top tension, half-turn dual-tip optodes |
| 2. Cap setup not optimal | Recheck cap size, stabilizers, cable tree routing, Velcro strap |
| 3. Probe placement vs. montage mismatch | Confirm physical stickers match grommet labels and the loaded montage |
| 4. Inter-optode distance too long | Recheck distances in NIRSite (should be ≤ ~4 cm) |
| 5. Environmental light interference | Use overcap / blackout cloth, dim the room |
| 6. Skull thickness | Use higher spring-top tension or more sensitive (APD) detectors |
| 7. Optode bundle not fully secured / wrong order | Reseat bundle connectors; check Sources A/B, Detectors A/B ports |
| 8. Broken optode | Run a static phantom test; swap in spare optode if confirmed faulty |

> **Quick read on the grid view:** a **horizontal red line** = broken source; a **vertical red line** = broken detector.

- Re-run optimization after each fix. If it improves, continue; if not, move to the next cause.
- Use **Refresh** for live feedback while making physical adjustments (source brightness won't re-adjust during Refresh) — run the full optimization (▶) again once you're done adjusting.
> **A comprehensive guide of troubleshooting related to signal:** [Refer to this manual](https://nirx.sharefile.com/share/view/sef0f1bc2ebb4723a)

---

## 4. Visual / Physiological Check
Before moving to recording, preview the live signal:
- Look for a **clear heartbeat-frequency oscillation** (~0.8–2 Hz, varies with the child's heart rate) in the raw trace.
- HbO variation should be noticeably larger than HbR, and the two should be loosely anti-correlated.
- Ask the participant to move slightly (if it won't disrupt the paradigm) to check for motion-artefact spikes.

> A clean heartbeat confirms physiological signal is being measured — but it does **not** guarantee a clean task response, since the real cortical signal is much weaker than the cardiac signal.

---

## 5. Before Proceeding to Recording
- [ ] Continuous/loop optimization mode is **stopped**
- [ ] All ROI channels at least acceptable (yellow), ideally green
- [ ] Heartbeat visible in raw trace
- [ ] No unresolved red/lost channels in your primary ROI

Next: [fNIRS Recording](./fNIRS-Recording)
