# DICOM Segmentation & 3D Reconstruction Pipeline

**Biomedical Engineering · UNITEC Honduras · Jennifer Bueso**

A Python-based pipeline for processing medical DICOM images — from raw CT series to segmented anatomical structures and 3D volumetric reconstruction, visualized in 3D Slicer.

---

## What it does

1. **DICOM loading** — reads CT series using `pydicom` and `SimpleITK`
2. **Preprocessing** — normalizes HU values, applies noise filtering
3. **Segmentation** — thresholding + region growing to isolate anatomical structures
4. **3D Reconstruction** — generates volumetric mesh for visualization in 3D Slicer
5. **Export** — outputs segmentation masks and 3D models (.nrrd / .stl)

---

## Results

- Processed CT series with **4+ anatomical structures** segmented per scan
- Reduced manual processing time to **under 3 minutes per series** with automated pipeline
- Validated visual accuracy against reference segmentations in 3D Slicer

---

## Tech stack

| Tool | Purpose |
|------|---------|
| `pydicom` | DICOM file reading and metadata parsing |
| `SimpleITK` | Image filtering, resampling, and segmentation |
| `NumPy` | Array operations and HU windowing |
| `Matplotlib` | Slice visualization and debugging |
| `3D Slicer` | 3D rendering and final validation |

---

## Setup

```bash
git clone https://github.com/jenniferbuesoo/dicom-segmentation
cd dicom-segmentation
pip install -r requirements.txt
```

**Requirements:**
```
pydicom>=2.3.0
SimpleITK>=2.2.0
numpy>=1.21.0
matplotlib>=3.5.0
```

---

## Usage

```python
from pipeline import DicomPipeline

# Load and process a CT series
pipeline = DicomPipeline(dicom_dir='path/to/ct_series/')
pipeline.load()
pipeline.preprocess(window_center=40, window_width=400)
pipeline.segment(threshold_hu=200)
pipeline.export_3d(output_path='output/reconstruction.nrrd')
```

---

## Project structure

```
dicom-segmentation/
├── pipeline.py          # Main processing pipeline
├── preprocessing.py     # HU normalization and filtering
├── segmentation.py      # Thresholding and region growing
├── visualization.py     # Slice plots and 3D export
├── requirements.txt
└── README.md
```

---

## Academic context

Developed as part of the Biomedical Engineering program at **UNITEC Honduras**.  
Focus area: medical image processing, diagnostic imaging technologies, and AI in healthcare.

---

## Author

**Jennifer Bueso**  
Biomedical Engineering Student — 5th year  
UNITEC · Tegucigalpa, Honduras  
[jennifer_bueso@hotmail.com](mailto:jennifer_bueso@hotmail.com) · [LinkedIn](https://linkedin.com/in/jennifer-bueso)

---

*Available for professional internship*
