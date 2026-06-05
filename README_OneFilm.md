# One Film, Many Futures

An annotated film frame dataset built from the 1959 public-domain horror film **House on Haunted Hill**, designed to explore the limits of modern object detection AI on historical, black-and-white cinematic material.

Built as part of the Creative Informatics and New Media Art course at the Department of Informatics and Telecommunications, University of the Peloponnese.

> *Can a general-purpose AI model trained on modern images understand gothic horror cinematography from 1959?*

---

## Overview

Existing object detection datasets (e.g. COCO) are trained on bright, modern, everyday images. This project investigates how **YOLOv8** performs when confronted with:

- Black-and-white footage
- Low-light and high-contrast shadow/light compositions
- Gothic architectural settings
- Historical props (skeletons, candelabras, period costumes)
- Human figures in states of emotional intensity and fear

---

## Dataset Statistics

| Metric | Value |
|---|---|
| Source film | House on Haunted Hill (1959) |
| Raw frames extracted | 447 |
| Curated frames (final dataset) | 130 |
| YOLO audit sample | 50 frames |
| Image resolution | 640×480 (640×640 after preprocessing) |
| Color | Black and white |

---

## Taxonomy

The dataset uses a **15-label annotation taxonomy** split into two categories:

### Visual Labels (8)
Objective, visually observable properties of the frame.

| Label | Description |
|---|---|
| `person` | Human figure present |
| `face` | Face clearly visible |
| `skeleton` | Skeleton prop present |
| `prop` | Historical/horror prop |
| `architecture` | Gothic architectural element |
| `shadow` | Dramatic shadow present |
| `light_source` | Visible light source (candle, lamp) |
| `multiple_figures` | More than one person in frame |

### Narrative Labels (7)
Subjective, story-driven properties requiring human interpretation.

| Label | Description |
|---|---|
| `fear` | Figure expressing fear |
| `threat` | Threatening presence in frame |
| `isolation` | Figure alone in an ominous setting |
| `confrontation` | Two or more figures in conflict |
| `mystery` | Ambiguous or suspenseful composition |
| `death` | Death-related imagery |
| `iconic_moment` | Key plot moment |

---

## Collection Process

- **Source:** [Internet Archive — House on Haunted Hill (1959)](https://archive.org/details/HouseOnHauntedHill1959) (Public Domain)
- **Extraction method:** Python + OpenCV, 1 frame per 10 seconds to avoid visual redundancy
- **Legal status:** Copyright-free — free to use and distribute for research purposes

---

## Curation Criteria

**Kept:**
- Frames with iconic horror props (skeleton, weapons)
- Close-ups capturing emotional intensity and fear expressions
- Frames with strong shadow/light contrast useful for AI testing

**Removed:**
- Pitch-black transition frames with no visual information
- Repetitive establishing shots of the house exterior

---

## Preprocessing

- **Duplicate removal:** Image Hashing algorithm to detect and remove near-identical consecutive frames
- **CSV cleaning:** Manual and automated validation of `annotations.csv` for syntax errors and missing values
- **Resize:** Images resized to YOLO input dimensions while preserving aspect ratio

---

## Object Detector Audit

A subset of **50 curated frames** was passed through **YOLOv8** to audit model performance on this type of material. The audit examined:

- Detection accuracy on low-light frames
- False positives/negatives on horror props
- Model confidence scores on black-and-white vs. color material

---

## Files

| File | Description |
|---|---|
| `annotations.csv` | Frame-by-frame annotation data |
| `double_annotation_log` | Cross-validation log between annotators |
| `dataset_card.md` | Structured dataset card |
| `one_film_many_futures_group15.zip` | Full project archive |

---

## Authors

**Dimitra Chrysikou** & **Nikolaos Dimopoulos**  
Group 15 — Creative Informatics and New Media Art  
Department of Informatics and Telecommunications  
University of the Peloponnese  

[github.com/dimitrachrysikou](https://github.com/dimitrachrysikou)
