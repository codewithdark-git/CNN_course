# CNN Course Lab

This repository contains the lab work for a **Convolutional Neural Networks
(CNNs)** course. It combines detailed explanations, executable PyTorch
implementations, experiments, visualizations, and a model-comparison project
for image classification.

The course is taught by **[Qazim Sajjad](https://github.com/qazimsajjad)**.
The lab work and repository are maintained by **[Ahsan umar](https://github.com/codewithdark-git)**.

## Project overview

The main project uses a 15-class subset of **CIFAR-100** to build and evaluate
image-classification models. The notebook starts with a CNN implemented from
scratch and then compares it with modern pretrained architectures on the same
task:

- Custom CNN
- ResNet50
- EfficientNet-B0
- Inception-V3
- Vision Transformer (ViT-Base/16)
- Swin-Tiny

The implementations are designed to connect the theory of CNNs with the
complete deep-learning workflow: preparing data, defining a model, training,
evaluating, visualizing, and interpreting results.

## Topics covered

The lab notebook explains and demonstrates:

- Image datasets, class labels, train/validation/test splits, and data loaders
- Image resizing, normalization, and data augmentation
- Convolutional layers, kernels, channels, feature maps, and receptive fields
- Activation functions, pooling, flattening, and fully connected layers
- Forward propagation and tensor-shape tracking
- Cross-entropy loss, backpropagation, optimizers, and learning-rate schedules
- Checkpointing, early stopping, and reproducible random seeds
- Transfer learning and pretrained computer-vision architectures
- CNN, transformer, and hybrid architecture differences
- Feature-map and patch visualization
- Accuracy, precision, recall, F1 score, and confusion matrices
- Error analysis and predictions versus ground truth
- Parameter count, training time, and accuracy trade-offs

## Repository contents

| File | Description |
| --- | --- |
| [`cnn_cifar100_model_comparison.ipynb`](./cnn_cifar100_model_comparison.ipynb) | Complete CNN implementation, 15-class CIFAR-100 experiment, and comparison of CNN and transformer models |
| [`vgg16_transfer_learning_cifar.ipynb`](./vgg16_transfer_learning_cifar.ipynb) | Lecture-style lab on VGG-16 transfer learning, freezing, fine-tuning, and feature visualization |
| [`LICENSE`](./LICENSE) | Custom MIT-style license and usage conditions |

Generated files such as `experiment_log.json` and `model_comparison.csv` may
also be produced when the notebook is executed. They contain experiment
outputs and comparison data, not source code.

## Dataset and experiment setup

The reference experiment uses:

- The first 15 classes of CIFAR-100
- 6,750 training images
- 750 validation images
- 1,500 test images
- A custom CNN trained with 32×32 inputs
- Pretrained models trained with 224×224 inputs, except Inception-V3 at
  299×299
- A fixed seed of 42 for reproducibility

The notebook downloads or prepares the dataset through the normal torchvision
workflow. A GPU is recommended, especially for the pretrained-model
comparison, but the custom CNN can be run on a CPU with a smaller experiment
configuration.

## Running the lab

### 1. Clone the repository

```bash
git clone https://github.com/codewithdark-git/CNN_course.git
cd CNN_course
```

### 2. Install the main dependencies

```bash
pip install torch torchvision torchaudio
pip install numpy pandas matplotlib seaborn scikit-learn tqdm
```

Use the PyTorch installation selector at
[pytorch.org](https://pytorch.org/get-started/locally/) if you need a
CUDA-specific command for your system.

### 3. Start Jupyter

```bash
pip install notebook
jupyter notebook
```

Start with [`cnn_cifar100_model_comparison.ipynb`](./cnn_cifar100_model_comparison.ipynb)
for the complete CNN project, then run
[`vgg16_transfer_learning_cifar.ipynb`](./vgg16_transfer_learning_cifar.ipynb)
for the focused transfer-learning lab. Run the cells from top to bottom. The
first run may take time because the dataset and pretrained model weights must
be downloaded.

## Suggested learning workflow

1. Read the explanation before running each section.
2. Record the input and output tensor shape after every major layer.
3. Run the custom CNN first and inspect its training curves.
4. Change one hyperparameter at a time and compare the result.
5. Inspect feature maps and the confusion matrix instead of relying only on
   accuracy.
6. Compare model quality against parameter count and training time.
7. Write your own observations about errors, overfitting, and trade-offs.

## License and usage condition

This repository is available under a **custom MIT-style license**. Before
using this material or learning from it, you must star the
[CNN_lab repository on GitHub](https://github.com/codewithdark-git/CNN_course).
See [`LICENSE`](./LICENSE) for the complete terms. This custom condition is
part of the license and is not part of the standard OSI MIT License.

## Learning outcomes

After completing this lab, a learner should be able to:

- Implement a CNN image classifier in PyTorch.
- Explain how convolution, pooling, and nonlinearities extract visual
  features.
- Build a reliable training and evaluation loop.
- Apply transfer learning with pretrained vision models.
- Select metrics appropriate for multiclass classification.
- Diagnose model behavior using curves, feature maps, and confusion matrices.
- Make an evidence-based comparison of accuracy, efficiency, and complexity.

If you use this material for learning, cite the original course guidance and
acknowledge this repository. When submitting coursework, write your own
observations and follow your instructor's submission and academic-integrity
requirements.
