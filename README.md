# AI CUP 2022 – Crop Status Monitoring by Image Recognition (TEAM_1927)

This repository contains the complete solution developed by **TEAM_1927** for the 2022 **AI CUP Autumn Contest – Crop Type Classification** (農地作物現況調查影像辨識競賽 秋季賽).  
We ranked in the **Top 25%** (32nd out of 446 teams) with a final private leaderboard score of **0.876**.

## Competition Background

In Taiwan, crop status surveys have traditionally relied on manual photography and annotation by field personnel. This is labor-intensive, time-consuming, and costly, especially as data volumes grow.

To accelerate and modernize this process, the AI CUP competition tasked participants with building models that can:
- Automatically classify images of agricultural land captured via UAV or satellite
- Identify **33 crop categories**
- Match expert-level classification performance

Participants received a large image dataset (~20GB) and were asked to develop an end-to-end AI pipeline that could replicate expert judgment under real-world conditions.

---

## Our Approach

### Data Preprocessing
- Unified various image dimensions to standard input sizes (400×400, 600×600, 800×800)
- Applied cropping, resizing, and augmentation
- Built custom pipelines for multiple preprocessing strategies

### Model Training
- Used **transfer learning** with pre-trained CNN architectures:
  - **Xception**, **DenseNet121**, **DenseNet201**
- Employed **layer freezing** followed by **fine-tuning**
- Optimized batch sizes based on GPU memory constraints

### Ensemble with TTA (Test-Time Augmentation)
- Performed inference with 6 image augmentations (flip, rotate, contrast boost)
- Combined predictions from three models using **majority voting**

### Evaluation Strategy
- Standard metrics: **accuracy**, **confusion matrix**, **classification report**
- Additional analysis using **Grad-CAM** to visualize model attention and confirm focus on relevant regions
- Special models trained for difficult cases like the “others” category

---

## Repository Contents

| Folder | Description |
|--------|-------------|
| `notebooks/` | Final submitted notebooks |
| `notebooks/experiments/` | Additional exploratory and test notebooks |
| `data/` | Expected data structure (not included) |
| `reports/` | Official team report |
| `certificate/` | Award certificate and metadata |

---

## Award

- **Top 25% Team** — 32nd / 446 teams on the private leaderboard
- [View Award Certificate](certificate/AICUP.pdf)

---

## Team

TEAM_1927  
Department of Mathematics (Information Mathematics Section)  
Fu Jen Catholic University, Taiwan

---

## License

This repository is shared for academic and portfolio purposes. Please contact us if you'd like to reuse any part of it.
