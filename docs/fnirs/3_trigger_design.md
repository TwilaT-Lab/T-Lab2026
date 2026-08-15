---
layout: default
title: Trigger Design
parent: fNIRS
nav_order: 3
---
# Trigger Design

*PsychoPy* handles stimulus presentation and trigger delivery to Aurora. Triggers mark the onset/offset of each condition or period of study so Satori can tell conditions/events apart during analysis.

## Trigger Options

| Method | Description |
|---|---|
| Manual | Hardware connection + Press F1–F12 keys |
| Wired | Hardware connection + PsychoPy |
| Wireless | Lab Streaming Layer (LSL) |

---
## 1. Manual Triggering
### Step 1 — Connect Hardware
![manualtrigger_hardware]({{ '/docs/images/manualtrigger_hardware.png' | relative_url }})
*Figure modified and adapted from NIRx fNIRS Training Slides.*

### Step 2 - Manually Input Trigger
- Assign different triggers to the F1–F12 keys. During recording, press the corresponding function key (F1–F12) whenever a trigger is required to insert a trigger marker into the recorded data.
- When a trigger is set successfully, a vertical line will appear on the on-going recording signal.

## 2. Wired Triggering 
Wired triggering allows trigger signals to be integrated directly into the PsychoPy program, enabling the stimulus presentation and trigger output to be synchronized.

Below is a simple example demonstrating how to incorporate trigger signals into a PsychoPy script.
### Part I. Integrate Trigger with PsychoPy 
**Step 1** 
Add a **Code Component** alongside stimulus. 
![Trigger_code_component]({{ '/docs/images/Trigger_code_component.png' | relative_url }})


**Step 2: Code Component → “Begin Experiment” tab**

- Initialize the connection between c-pod and PsychoPy. 
- After c-pod is found, set trigger last 20ms, and buffer for 50ms.

```python
import serial
import serial.tools.list_ports
import struct
import time

def find_cpod():
    for p in serial.tools.list_ports.comports():
        try:
            ser = serial.Serial(p.device, baudrate=115200, bytesize=8,
                                 parity='N', stopbits=1, timeout=0.5)
            ser.write(b'_c1')
            time.sleep(0.05)
            response = ser.read(10)
            if b'_xid' in response:
                return ser
            ser.close()
        except Exception:
            continue
    return None

cpod = find_cpod()
if cpod is None:
    print("C-POD is not detected.")
else:
    cpod.write(b'mp' + struct.pack('<I', 20))
    time.sleep(0.05)
```

**Step 3: Code Component → “Begin Routine” tab**

Ensure trigger has not sent when begin the routine. 
```python
trigger_sent = False
```

**Step 4: Code Component → “Each Frame” tab**

This part of code enables co work of stimulus presented through psychopy and trigger sent out.
```python
# Send the trigger when the stimulus starts
if text_stim.status == STARTED and not trigger_sent:

    # Send trigger code through c-pod
    if cpod is not None:
        cpod.write(b'mh' + struct.pack('<H', 1))
        print(f"Trigger 1 sent at {t:.4f}s")

    # Send a error message when trigger sending fails
    else:
        print(f"Trigger 1 should be sent at {t:.4f}s ")

    #Ensure trigger send only once.
    trigger_sent = True
```

**Step 5: Code Component → “End Experiment” tab**

Disconnect C-Pod.
```python
if cpod is not None:
    cpod.close()
```

### Part II: Hardware Connection
The equipment set up that is compatible to the code above is shown below.

**Explanation:**
- The NIRSport2 host, Trigger Box, and C-Pod are connected in the same configuration as for manual triggering. 
- The hardware is connected via cables to the computer running PsychoPy, which presents the stimuli and sends the trigger signals. 
- A second computer runs Aurora to wirelessly record and visualize the fNIRS data.

![PsychoPy_trigger_hardware]({{ '/docs/images/PsychoPy_trigger_hardware.png' | relative_url }})

---

## 3. Wireless Triggering via LSL

LSL synchronizes data and triggers over the same Wi-Fi/router network already used for the Aurora device connection. This method is particularly suitable for hyperscanning experiments in which a presentation PC delivers stimuli to both participants performing time-sensitive tasks simultaneously.

- In Aurora's configuration, set the **Trigger in** stream name (default: `"Trigger"`).
- The stream name on the **PsychoPy side must match exactly** — a mismatch silently drops all triggers.
- Use Aurora's **Test Connection** button to confirm the stream is live before recording.

> **Recommended order:** Start Aurora first → record a few seconds of baseline → then start the PsychoPy script. Confirm the LSL stream name matches on both sides **every session**, not just the first time.

---
> Note: *Trigger files are saved automatically: `*_lsl.tri` (LSL/manual) and 
`*.tri` (hardware) in the recording's data folder.*
