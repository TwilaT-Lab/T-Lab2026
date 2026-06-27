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
