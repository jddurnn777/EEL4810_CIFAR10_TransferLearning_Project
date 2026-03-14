# EEL4810_CIFAR10_TransferLearning_Project
PyTorch-based CIFAR-10 image classification project comparing a baseline CNN trained from scratch with transfer learning using pretrained ResNet-18. Includes frozen and fine-tuned experiments, evaluation metrics, plots, checkpoints, and results for our team project.

# Project Descriotion
This project compares a baseline convolutional neural network (CNN) trained from scratch with transfer learning using a pretrained ResNet-18 on the CIFAR-10 dataset. We evaluate whether pretrained visual features improve image classification accuracy and whether fine-tuning performs better than using frozen pretrained layers.

# Objective
The goal of this project is to determine whether transfer learning improves CIFAR-10 image classification performance compared to a simple CNN trained from scratch. We also compare frozen-feature transfer learning against fine-tuning.

# Dataset
We use the CIFAR-10 dataset, which contains 60,000 32x32 color images across 10 classes:
- airplane
- automobile
- bird
- cat
- deer
- dog
- frog
- horse
- ship
- truck

# Models
1. Baseline CNN trained from scratch
2. Pretrained ResNet-18 with frozen backbone
3. Pretrained ResNet-18 with fine-tuning

# Ablation Study
Our ablation compares:
- frozen pretrained layers
- fine-tuned pretrained layers

This helps us measure whether allowing the pretrained network to adapt improves performance.

# Evaluation
The main evaluation metric is accuracy. We also use plots and a confusion matrix to compare model behavior and class-level performance.

# Repository Structure
text
notebooks/
  01_baseline_cnn.ipynb
  02_resnet_transfer_learning.ipynb
  03_evaluation_and_figures.ipynb

checkpoints/
results/
figures/
reports/

# How to Run
1. Open the notebooks in Google Colab.
2. Enable GPU runtime.
3. Run `01_baseline_cnn.ipynb` to train the baseline model.
4. Run `02_resnet_transfer_learning.ipynb` to train the frozen and fine-tuned ResNet-18 models.
5. Run `03_evaluation_and_figures.ipynb` to generate comparison tables, plots, and confusion matrices.

# Requirements
- Python
- PyTorch
- TorchVision
- NumPy
- Matplotlib
- scikit-learn
- Google Colab with T4 GPU

# Team Members
- Member 1: Dataset preparation and preprocessing
- Member 2: Baseline CNN implementation
- Member 3: ResNet transfer learning and ablation
- Member 4: Evaluation, figures, and report integration

# References
- CIFAR-10 Dataset: https://www.cs.toronto.edu/~kriz/cifar.html
- ResNet Paper: https://arxiv.org/abs/1512.03385
- PyTorch CIFAR-10 Tutorial: https://docs.pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html
- PyTorch Transfer Learning Tutorial: https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html
