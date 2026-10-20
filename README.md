# Learned Stage-Wise Curvature Tuning

This repository contains the learned Stage-Wise Curvature Tuning (SW-CT)
study with ImageNet-pretrained ResNet-18 and ResNet-50.

## Experiments

- Baseline: original ReLU backbone and downstream linear classifier.
- S-CT: one global beta chosen using validation accuracy.
- Learned SW-CT: four stage betas with fixed initialization at 0.78.
- Learned SW-CT: four stage betas with random initialization in [0.70, 0.99].
- Seeds: 42, 43, and 44. Training budgets: 20 and 30 epochs.
- Datasets: Beans, DTD, Flowers102, Imagenette, FGVC Aircraft, Arabic Digits,
  CUB200, PathMNIST, DermaMNIST, Arabic Characters, FashionMNIST, Food101,
  and OCTMNIST.

## Repository contents

- `src/curvature-tuning/`: experiment scripts, training code, and utilities.
- `notebooks/Learned SW-CT/Resnet-18/`: completed ResNet-18 notebooks.
- `notebooks/Learned SW-CT/Resnet-50/`: completed ResNet-50 notebooks.
- `results/`: original result JSON files found locally, if available.
- `summaries/`: Excel summaries found in the selected local result folders, if available.

This preparation copied 26 notebooks and 0 result JSON files.
Notebook outputs are retained as recorded. Some outputs may have been recovered
from saved experiment logs. Updating a setup cell does not rerun the experiment.

Formula-SWCT and exploratory beta-probe experiments are outside this release.

## Running experiments

Clone `https://github.com/NiftySnek173/research-curvature-tuning.git`, then work from
`src/curvature-tuning` before running the scripts. Notebook setup cells use
the `main` branch and `/content/research-curvature-tuning` on remote Linux GPU servers.

Use the Python environment and compatible CUDA-enabled PyTorch/torchvision
versions used for the experiments, then install the remaining dependencies:

```bash
python -m pip install -r requirements.txt
```

`requirements.txt` does not pin every environment component. Record the actual
Python, PyTorch, torchvision, Pillow, CUDA, and GPU versions alongside the
results; version numbers have not been inferred by this preparation script.

For exact batch sizes and configurations, use each dataset notebook.
The scripts are `generalization_ct.py` and `generalization_stagewise_ct.py`.

## Attribution

This work extends **Curvature Tuning: Provable Training-free Model Steering
From a Single Parameter**, by Leyang Hu, Matteo Gamba, and Randall Balestriero
(NeurIPS 2025).

- Original implementation: https://github.com/Leon-Leyang/curvature-tuning
- Original paper: https://proceedings.neurips.cc/paper_files/paper/2025/hash/57cc9268e06500c7681e58829dca4a07-Abstract-Conference.html

The baseline implementation and learned SW-CT extension should be attributed
separately. Existing source notices are retained. No new license has been
assigned to third-party code by this preparation script.
