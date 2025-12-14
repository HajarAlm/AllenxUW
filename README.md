# AllenxUW – Predictive Processing in Mouse V1

This repo contains code and notebooks for my EE P 596 (Computer Vision) project, where I analyze data from the **OpenScope Community Predictive Processing** project at the Allen Institute.

The goal is to build a small end-to-end pipeline that goes from **images and behavior** to **trial-aligned neural responses** in mouse primary visual cortex (V1):

- Phase 1: Computer vision & behavior  
  - Segment the cranial window from a surface image  
  - Visualize eye-tracking (pupil trajectory) and wheel motion  
- Phase 2: Neural analysis  
  - Build a clean trial table  
  - Compute PSTHs and orientation tuning curves  
  - Explore mismatch (prediction-error) responses

---

## Data

The notebooks assume access to an **OpenScope Community Predictive Processing** NWB file for a single session (Neuropixels + behavior + surface image).

You’ll need to:

1. Download the NWB file and associated images/behavior files from the OpenScope project.
2. Update any file paths in the notebooks to point to your local copy.

*(The dataset itself is **not** stored in this repo.)*

---

## Environment

Typical requirements (install with `pip` or `conda`):

- Python 3.9+
- Jupyter / Colab
- `numpy`, `pandas`, `matplotlib`, `seaborn`
- `pynwb` (or relevant NWB reader)
- `h5py`
- `opencv-python` (for image processing)
- `scipy`

You can run these notebooks either locally (Jupyter) or in Google Colab.

---

## Notebooks

**00_intro_ephys_nwb.ipynb**  
Basic exploration of the NWB file: sessions, units, spike times, and trial structure.

**10_p3_trial_table_and_labels.ipynb**  
Builds a clean trial table with stimulus identity, standard vs mismatch labels, and stimulus onset times.

**11_p3_psth_and_tuning.ipynb**  
Computes peri-stimulus time histograms (PSTHs) for a single unit and constructs orientation tuning curves from standard trials.

**12_p3_novelty_models.ipynb**  
(Scratch / exploratory) First attempts at comparing standard vs mismatch responses and setting up novelty / prediction-error model fits.

**13_p3_cranial_image_cv.ipynb**  
Computer vision analysis of the cranial surface image:
- Grayscale conversion and intensity histogram  
- Thresholding + morphology  
- Cranial-window contour extraction  
- Pupil-trajectory visual
