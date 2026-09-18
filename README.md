# SCIGA: Scaling-Cross Integrated Gradient Attack

Anonymized artifact for the IEEE SaTML 2027 submission
"SCIGA: Scaling-Cross Integrated Gradient Attack".

SCIGA generates adversarial examples (AEs) that remain effective after the
input image is resized or super-resolved before classification. It uses
Integrated Gradients to aggregate gradient information across multiple
resizing scales during AE generation.

## Contents

This repository will contain:

- The implementation of SCIGA and of the baselines (I-FGSM, AMSA) used in the paper.
- The script that reproduces the 3,000-image sample of the ImageNet validation set.
- The evaluation scripts for the three evaluation perspectives:
  Scale-Crossing Attack Capability, Scale-Wise Transferability,
  and Resizing-Method-Wise Transferability.
- Configuration files fixing all attack hyper-parameters reported in the paper.

## Experimental Setting

| Item | Value |
|------|-------|
| Target model | ResNet50 (with GAP), ImageNet-pretrained, from torchvision |
| Dataset | 3,000 images from the ImageNet validation set, correctly classified at 0.5x, 1x and 2x, center-cropped to 320x320 |
| Resizing methods | Bilinear, Area, Bicubic (`torch.nn.functional.interpolate`) |
| Target scales S_T | 0.5, 0.6, 0.7, 0.8, 0.9, 1.0, 1.25, 1.5, 1.75, 2.0 |
| Non-target scales S_N | 0.55, 0.65, 0.75, 0.85, 0.95, 1.35, 1.85 |
| Perturbation limit epsilon | 8, 12, 16 |
| Iterations I | 40 |
| Step size alpha | epsilon / 20 |
| Batch size | 20 |

## Requirements

- Python 3
- PyTorch and torchvision
- ImageNet validation set (not redistributed; obtain it from the official source)

## Usage

Instructions for running AE generation and evaluation will be added together
with the code.
