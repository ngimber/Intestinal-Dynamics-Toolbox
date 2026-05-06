# Intestinal Dynamics Toolbox (IDT)
**Automated Motion Tracking and Calcium–Movement Coupling Analysis in Drosophila Intestines**

The **Intestinal Dynamics Toolbox (IDT)** provides Python/Jupyter tools for quantifying movement dynamics in *Drosophila* intestines and relating mechanical motion to calcium activity.  
IDT contains two complementary analysis pipelines:

- **IntestiTrack** — skeleton-based tracking of intestinal motion from time-lapse autofluorescence recordings  
- **CaMotion** — correlation-based motion quantification and alignment of calcium transients with movement

These tools are designed for reproducible processing of single-color motion imaging and dual-color (calcium + motion) recordings.
The full methods are described in Pampaloni et al. 2026

---

## Toolbox Components

### **1. IntestiTrack — Skeleton-Based Motion Extraction**
**Goal:** Quantify intestinal movement by reducing segmented images to skeletons and measuring angular changes over time.

**Processing workflow:**
1. **Segmentation** using Otsu’s method  
2. **Skeletonization & pruning** to remove spurious branches  
3. **Motion quantification** via angular deformation analysis  
4. **Visualization** through skeleton overlays  
5. **Summary metrics** using histograms of frame-to-frame angular change

---

### **2. Ca Motion — Calcium–Movement Correlation from Dual-Color Imaging**
**Goal:** Quantify motion using frame-to-frame correlation and relate it to calcium transients.

**Processing workflow:**
1. **Segmentation** of autofluorescence frames  
2. **Motion metric:**  
   `movement = 1 – Pearson correlation(frame_t, frame_{t–1 s})`  
3. **Calcium peak detection** using SciPy `find_peaks`  
4. **Temporal alignment** of movement and calcium traces to peak fluorescence  
5. **Normalization and averaging** across events

---


## Usage

### **IntestiTrack**
1. Open `IntestiTrack.ipynb` in Jupyter
2. Change path="......" to the required data path
3. Run all cells

### **CaMotion**
1. Open `CaMotion.ipynb`
2. Change path="......" to the required data path
4. Run all cells

---

## 📚 Citing IDT
If you use IDT in your research, please cite:
Pampaloni et al. ...

