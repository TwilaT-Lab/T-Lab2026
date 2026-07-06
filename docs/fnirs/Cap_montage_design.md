---
layout: default
title: Cap Montage Design
parent: fNIRS
nav_order: 3
---
## Create Montage Template for Aurora

**Software:** NIRSite

1. **Select Head Model**
   Use "Adults" if the participant is older than 8 months.

2. **Choose Layout View**
   The interface defaults to a 3D model. Switch to 2D layout to select a 
   standard position (e.g., the 10-10 system). The 3D interface only 
   allows arbitrary positioning.

3. **Optode Placement & Configuration**
   - `Shift + Click` once → assigns **Source**
   - `Shift + Click` twice → assigns **Detector**
   - `Shift + Click` three times → **Cancels** (circle turns green, 
     indicating the position is not recorded)
   - Numbers (e.g., S1, S2...) appear in the order they were clicked
   - A purple line will appear between a source and a detector once 
     paired (1 detector can connect to up to 3 sources)

   > **Note:** Be mindful of the fNIRS bundle constraints — S1 and S2 
   > cannot be placed too far apart, and each detector may only connect 
   > to a maximum of 3 sources. If no line appears between a source and 
   > detector, check the distance between them.

4. **Upload / Save**
   Under "Save," choose **"Export to Aurora,"** or alternatively save 
   as a document and open it directly in Aurora.

   ---
 ## Related Papers

### Executive Function (EF), Inhibitory Control

Go/NoGo task based fNIRS recording for children.

**Citation:** Shah, L., Zhou, X., DiPiero, M.A. et al. Neural Correlates of Inhibitory Control in Children: Evidence Using MRI and fNIRS. *Brain Topogr* 38, 54 (2025). https://doi.org/10.1007/s10548-025-01129-8

![image1]({{ "/images/image1.png" | relative_url }})

---

### Phonological Awareness

Phonological awareness in Chinese-English bilingual children, aged 6–7.

**Citation:** Li, Y.L., Fan, L.Y., Chen, H.C., Chen, S.Y., Kovelman, I., Chou, T.L. Developmental changes in phonological awareness in Chinese-English bilingual children: An fNIRS longitudinal study. *NeuroImage*, Volume 321, 2025, 121522. https://doi.org/10.1016/j.neuroimage.2025.121522

![Phonological awareness task design]({{ "/images/phonological-awareness/task-design.png" | relative_url }})

---

### Reading

Sentence, word list, jabberwocky, and non-word list reading for adults.

**Citation:** Čeko, M., Hirshfield, L., Doherty, E. et al. Cortical cognitive processing during reading captured using functional near-infrared spectroscopy. *Sci Rep* 14, 19483 (2024). https://doi.org/10.1038/s41598-024-69630-x

![Reading task stimuli examples]({{ "/images/reading/stimuli-examples.png" | relative_url }})

---

### Neural Synchrony, Parent-Child Interaction

fNIRS hyperscanning for parent-child play/motor-related game, ASD & typically developing children.

**Citation:** Kruppa, J.A., Reindl, V., Gerloff, C., Oberwelland Weiss, E., Prinz, J., Herpertz-Dahlmann, B., Konrad, K., Schulte-Rüther, M. Brain and motor synchrony in children and adolescents with ASD—a fNIRS hyperscanning study. *Social Cognitive and Affective Neuroscience*, Volume 16, Issue 1-2, January-February 2021, Pages 103–116. https://doi.org/10.1093/scan/nsaa092

![Parent-child hyperscanning setup]({{ "/images/parent-child-interaction/hyperscanning-setup.png" | relative_url }})

---

### Neural Synchrony, Parent-Child Shared Reading

fNIRS hyperscanning for parent-child shared reading, 19–46 month-old children.

**Citation:** Zhai, Y., Xie, H., Zhao, H., Wang, W., Lu, C. Neural synchrony underlies the positive effect of shared reading on children's language ability. *Cerebral Cortex*, Volume 33, Issue 19, 1 October 2023, Pages 10426–10440. https://doi.org/10.1093/cercor/bhad293

![Parent-child shared reading setup]({{ "/images/shared-reading/task-setup.png" | relative_url }})

---

### Neural Synchrony, Parent-Child Collaborative Drawing

fNIRS hyperscanning for parent-child collaborative task (the Etch-a-Sketch joint drawing task), focused on dorsolateral prefrontal cortex (dlPFC) & temporoparietal junction (TPJ), 6–11 year-old children.

**Citation:** Zhai, Y., Xie, H., Zhao, H., Wang, W., Lu, C. Neural synchrony underlies the positive effect of shared reading on children's language ability. *Cerebral Cortex*, Volume 33, Issue 19, 1 October 2023, Pages 10426–10440. https://doi.org/10.1093/cercor/bhad293

![Collaborative drawing task (Etch-a-Sketch)]({{ "/images/collaborative-drawing/etch-a-sketch-task.png" | relative_url }})
