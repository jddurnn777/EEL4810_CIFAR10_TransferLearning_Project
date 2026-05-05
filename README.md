# EEL 4810 – CIFAR-10 Transfer Learning Project

## Overview  
This project explores how different deep learning approaches perform image classificaiton using both the CIFAR-10 dataset and the MNIST dataset.  

The primary goal was to compare the performance of a fine-tuned CNN against a Vision Transformer, with a strong focus on how transfer learning impacts performance and generalization under limited data and compute constraints.

The following models were implemented and compared:
- A baseline CNN trained from scratch  
- A pretrained :contentReference[oaicite:3]{index=3} used as a feature extractor (frozen layers)  
- A pretrained ResNet-18 fine-tuned end-to-end  
- A :contentReference[oaicite:4]{index=4} baseline  

---

## Repository Structure  
EEL4810_CIFAR10_TransferLearning_Project/
│
├── 01_baseline_cnn.ipynb # CNN trained from scratch
├── 2_baseline_cnn.ipynb # Transfer learning (frozen layers)
├── 3_baseline_cnn.ipynb # Transfer learning (fine-tuned)
├── VIT_baseline4.ipynb # Vision Transformer baseline
│
├── README.md # Project documentation
├── requirements.txt # Dependencies
└── .gitignore


---

## Setup Instructions  

Clone the repository:
```bash
git clone https://github.com/jddurnn777/EEL4810_CIFAR10_TransferLearning_Project.git
cd EEL4810_CIFAR10_TransferLearning_Project

pip install -r requirements.txt


# Datasets 

This project uses two datasets:

##CIFAR-10

Used for all CNN-based models:

Baseline CNN
Frozen ResNet-18
Fine-tuned ResNet-18

- CIFAR-10 contains:
    - 60,000 color images
    - 10 classes
    - 50,000 training / 10,000 test images

## MNIST
Used for the Vision Transformer baseline
- MNIST contains:
    - Grayscale handwritten digit images
    - 10 classes
- MNIST was used instead of CIFAR-10 for the Vision Transformer due to time constraints and loading/debugging issues. It allowed successful implementation of the transformer pipeline while keeping the dataset simpler.


# Methods
1. Baseline CNN: A simple convolutional neural network trained from scratch on CIFAR-10.
2. Transfer Learning with frozen hidden layers on REsNet-18: A pretrained ResNet-18 used as a feature extractor with frozen convolutional layers. Only the final classification layer was retrained.
3. Transfer Learning with Fine-Turned ResNet-18: A pretrained ResNet-18 with all layers unfrozen, allowing full adaptation to CIFAR-10.
4. Vision Transformer: A Vision Transformer baseline trained on MNIST using a patch-based representation of images.

## Results Summary

| Model | Dataset | Test Accuracy | F1 Score | Notes |
|---|---|---:|---:|---|
| Baseline CNN | CIFAR-10 | 79.96% | N/A | Trained from scratch |
| Frozen ResNet-18 | CIFAR-10 | 77.45% | N/A | Used as a feature extractor with frozen layers |
| Fine-Tuned ResNet-18 | CIFAR-10 | **94.47%** | **0.94** | Best-performing CNN model |
| Vision Transformer | MNIST | **99.20%** | **0.99** | Trained on MNIST due to CIFAR-10 loading/debugging issues |

**Note:** The Vision Transformer was trained on MNIST, while the CNN models were trained on CIFAR-10. Because the datasets are different, the ViT result should not be treated as a direct comparison against the CNN baselines.

# Trained Model Checkpoint
Due to time restraints, we were not able to save the best model to a path. However, we have documented in the notebooks in GIT for the first three baselines very well and in the appendix of the report, there will be a file with screenshots from our notebooks directly.

## Key Takeaways

- Transfer learning improved performance compared to training a CNN from scratch.
- Fine-tuning ResNet-18 produced the strongest CIFAR-10 results.
- Pretrained models helped improve training stability and generalization.
- The Vision Transformer pipeline worked successfully on MNIST, but it would need to be trained on CIFAR-10 for a fair comparison.

## Notes

This project was completed under time and compute constraints.

CIFAR-10 was used for the CNN and transfer learning experiments. MNIST was used for the Vision Transformer baseline because CIFAR-10 caused loading and debugging issues during implementation.

Because the datasets are different, the CNN and ViT results should not be interpreted as a direct one-to-one comparison.

## Author

**Jennifer D.**  
