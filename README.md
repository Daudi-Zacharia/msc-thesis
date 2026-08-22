# Deep Learning and xAI applied to TB Screening

MSc Data Science thesis code: custom and pretrained CNNs, plus a ViT-B/16
baseline, for tuberculosis screening from chest X-rays, across a small dataset
(704 images, **D1**) and a moderately large one (4200 images, **D2**). Lung
segmentation with a U-Net is used to test whether restricting the classifier
to the lung field improves detection, and Grad-CAM and t-SNE are used to check
what the models actually learned.

## Documents

The thesis PDF is linked below


[![Google Drive](https://img.shields.io/badge/Google%20Drive-Thesis%20PDF-DF4B37?logo=googledrive&logoColor=white)](https://drive.google.com/file/d/1vFm7FgCC8NLXUbbpsZj0X4If5L_MyxfC/view?usp=drive_link)

## Layout

```
msc-thesis/
├── classification/
│   ├── clean_notebooks/     readable reproduction path
│   └── raw_notebooks/       original experimentation, untouched
└── segmentation/
    ├── clean_notebooks/
    └── raw_notebooks/
```

**`raw_notebooks/` is the source of truth.** These are the original
experimentation notebooks exactly as they were run, including the exploratory
runs, dead ends and superseded checkpoints. Nothing in them has been edited —
they are kept for provenance, and the git history of every one of them is
preserved back to January 2026.

**`clean_notebooks/` is the readable path.** Rebuilt from the raw notebooks,
covering only the runs reported in the manuscript. Helper functions, model
definitions and transforms are each defined once near the top, so the per-model
sections are short and differ only in which model, checkpoint, transform and
dataloader they use.

*If a notebook fails to render on GitHub, use its "Open in Colab" badge.*

### Clean notebooks

| Notebook | Covers | Link |
| :--- | :--- | :--- |
| **d1_experiments** | D1 (704), 5 CNNs × {original, segmented} — Table III, plus an exploratory ViT-B/16 baseline | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/clean_notebooks/d1_experiments.ipynb) |
| **d2_experiments** | D2 (4200), 5 CNNs × {no aug, aug, oversampling, segmented} — Table IV, plus a ViT-B/16 baseline and the manuscript t-SNE / Grad-CAM figures | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/clean_notebooks/d2_experiments.ipynb) |
| **cross_dataset_evaluation** | D1→D2 and D2→D1 generalisation for the five CNNs and ViT-B/16, with per-task confidence intervals | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/clean_notebooks/cross_dataset_evaluation.ipynb) |
| **data_leakage_analysis** | Cross-dataset duplicate detection via perceptual hashing | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/clean_notebooks/data_leakage_analysis.ipynb) |
| **segmentation_unet** | The VGG16-BN U-Net (`seg_unet_2.pth`) used by every segmented scheme | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/segmentation/clean_notebooks/segmentation_unet.ipynb) |
| **quantitative_d2_segmentation** | No-reference mask quality on D2, where no ground-truth masks exist | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/segmentation/clean_notebooks/quantitative_d2_segmentation.ipynb) |

Run order, if starting from scratch: `segmentation_unet` produces the U-Net that
`d1_experiments` and `d2_experiments` both depend on for their segmented schemes.

### Raw notebooks

| Notebook Name | Description | Link |
| :--- | :--- | :--- |
| **Classification Custom CNNs** | Training custom CNN models for classification. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/Classification_Custom_CNNs.ipynb) |
| **Classification Segmented Lungs** | Training custom CNN models on segmented lung images. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/Classification_Segmented_Lungs_Custom_CNN.ipynb) |
| **DenseNet169** | Transfer learning experiments using DenseNet169. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/DenseNet169.ipynb) |
| **EfficientNet B3** | Transfer learning experiments using EfficientNet B3. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/EfficientNet_B3.ipynb) |
| **ResNet50** | Transfer learning experiments using ResNet50. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/ResNet50.ipynb) |
| **VGG 16** | Transfer learning experiments using VGG 16. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/classification/raw_notebooks/VGG_16.ipynb) |
| **Segmentation Custom CNN** | Custom CNN architecture for lung segmentation. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/segmentation/raw_notebooks/Segmentation_Custom_CNN.ipynb) |
| **Segmentation Inference** | Running inference and generating lung masks using trained models. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/segmentation/raw_notebooks/Segmentation_Inference.ipynb) |
| **Segmentation Unet Full** | Full implementation of U-Net for lung segmentation. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Daudi-Zacharia/msc-thesis/blob/main/segmentation/raw_notebooks/Segmentation_Unet_Full.ipynb) |

## ViT-B/16 baseline

A Vision Transformer (`vit_b16`, ImageNet-1k pretrained) is included alongside
the five CNNs as an exploratory baseline — a working, reasonably tuned setup to
check whether ViT is viable at these dataset sizes, not a final polished
result. It lives in its own section of each notebook, with its own checkpoint
dictionary and results table, so it does not touch the five-CNN tables
reported in Table III / Table IV.

Two fine-tuning strategies are compared per scheme: a **frozen backbone**
(only the new classification head trains) against **full fine-tuning**
(everything trains). Full fine-tuning wins on every scheme it was compared
against, on both datasets, so it is the only strategy used for schemes added
after that comparison:

- **`d2_experiments`** — all four D2 schemes, six runs total. No Aug. and With
  Aug. compare frozen vs. full fine-tune; Oversampling and Segmented are
  trained full-fine-tune only, once the comparison was settled.
- **`d1_experiments`** — both D1 schemes, four runs total, comparing frozen vs.
  full fine-tune on each. Re-run here rather than assumed from the D2 result:
  D1 has far less training data (492 images vs. D2's 3360), which is exactly
  the regime where a frozen backbone can plausibly win. It still doesn't, but
  far less decisively than on D2. D1 has no Oversampling scheme for any model,
  ViT included, since its two classes are already balanced.
- **`cross_dataset_evaluation`** — extends every task to ViT: in-domain
  evaluation on each dataset's own test split, D1→D2 across both D1 schemes,
  and D2→D1 using D2's best-scoring scheme (With Aug.). Confidence intervals
  follow whichever method fits the task — bootstrap F1 (with an automatic
  Wilson-accuracy fallback for a flawless run) for in-domain D2 and the D1→D2
  direction, a direct Wilson accuracy CI for D2→D1, and no CI at all for D1
  in-domain (72 test images) — left to be computed externally from the
  reported confusion-matrix counts.

Checkpoints follow `vit_b16_d{1,2}_{scheme}_{frozen|full_ft}.pt`.


## Data

Both datasets are downloaded by the notebooks themselves via `kagglehub`:

- **D1** — 704 chest X-rays *with* ground-truth lung masks
  (`iamtapendu/chest-x-ray-lungs-segmentation`). Split 70/20/10.
- **D2** — 4200 chest X-rays, 700 TB and 3500 Normal, no masks
  (`tawsifurrahman/tuberculosis-tb-chest-xray-dataset`). Split 80/10/10.

## Reproducing results

The clean notebooks have been **verified to run end-to-end with synthetic data**
on CPU: every code cell executes, shapes stay consistent through the pipeline,
the training loop produces a loss, evaluation produces a metrics dict, Grad-CAM
produces a heatmap and t-SNE produces a 2-D embedding. That check validates
**code correctness only** — it does *not* reproduce the published numbers, which
require the real images, the real trained checkpoints and a GPU.

**Trained checkpoints are not included in this repository.** They live in Google
Drive and must be obtained separately. Each notebook lists the checkpoints it
needs in a table in its opening cell and in its `CHECKPOINTS` dictionary. The
expected locations are:

```
/content/drive/MyDrive/MSc Data Science/Thesis/Codes/classification
/content/drive/MyDrive/MSc Data Science/Thesis/Codes/segmentation
```

To reproduce the published results, either:

1. **Place the checkpoints in a Google Drive folder** and update
   `path_classification` / `path_segmentation` in the notebook's Setup section to
   point at it, or
2. **Upload the checkpoints into the Colab session's local storage** for that run
   and point the same two variables at the local directory.

A **GPU runtime is required**. The training cells are kept for reproducibility
but are not meant to be re-run on every pass — each Evaluation cell loads the
saved checkpoint instead, which is the fast path.

## Notes carried over from the raw notebooks

A few quirks are reproduced deliberately, because changing them would no longer
match the checkpoints that produced the published numbers:

- **EfficientNetB3 on D1** trains at 300×300 but is evaluated at 224×224.
- **The segmented schemes use a different split** from their unsegmented
  counterparts: the whole dataset is segmented first, then the ROI images are
  split 70/20/10 from `os.listdir()` order. On D2 this still yields a 420-image
  test set (70 TB + 350 Normal), the same size as the 80/10/10 split, but not the
  same images.
- **The D2 Custom CNN checkpoints were trained without normalization**, unlike
  their D1 counterparts, and the three unsegmented ones are stored as state
  dicts rather than full model objects.
