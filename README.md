# From Introduction to Advanced Deep Learning

This repository contains the lab material for a final-year undergraduate
deep-learning course. The course is organized as a **topic-level roadmap**:
each topic is taught for four contact hours and ends with its own project,
dataset, and problem statement.

The course is led by **[Dr. Muhammad Sajad](https://github.com/qazimsajjad)**.
The material is presented and maintained by
**[Ahsan Umar](https://github.com/codewithdark-git)** as instructor, lab
instructor, and teaching assistant.

## Course at a glance

- **Contact hours:** 4 hours per topic, 7 topics, 28 hours total
- **Core track:** Topics 1–4, with six mandatory projects (P1–P6)
- **Optional track:** Topics 5–7, with six optional projects (P7–P12)
- **Stack:** Python, PyTorch, torchvision, and OpenCV
- **Advanced elective:** Diffusion and flow matching inside Topic 6

The mandatory core progresses from fully connected networks to CNN
classification, object detection, and recurrent sequence models. The optional
track extends that foundation to dense prediction and tracking, generative
models, and production deployment.

## Roadmap

| Topic | Area | Track | Projects |
| --- | --- | --- | --- |
| 1 | Artificial Neural Networks (ANN) | Core | P1 MNIST, P2 California Housing |
| 2 | CNNs: Image Classification | Core | P3 CIFAR-10 |
| 3 | CNNs: Object Detection | Core | P4 Pascal VOC |
| 4 | Recurrent Neural Networks and Sequence Models | Core | P5 Multi30k translation, P6 IMDB |
| 5 | Segmentation and Object Tracking | Optional | P7 Oxford-IIIT Pet, P8 MOT17 |
| 6 | Generative Models: AE, VAE, Diffusion, Flow Matching | Optional | P9 corrupted MNIST, P10 CIFAR-10 or CelebA |
| 7 | Knowledge Distillation and Deployment | Optional | P11 CIFAR-100, P12 Pascal VOC |

### Topic 1 — Artificial Neural Networks

Build, regularize, and diagnose fully connected networks from scratch.
Coverage includes perceptrons and artificial neurons, nonlinear activations,
loss functions, computational graphs, backpropagation, gradient checking,
optimizers, learning-rate schedules, dropout, normalization, checkpoints,
reproducibility, and under/over-fitting diagnosis.

- **P1 (mandatory):** Classify handwritten digits from raw 28×28 pixels with
  an MLP on MNIST, including loss-curve diagnosis.
- **P2 (mandatory):** Predict a continuous target on California Housing using
  feature scaling, MSE loss, and R²/MAE reporting.

### Topic 2 — CNNs: Image Classification

Move from convolution arithmetic and receptive fields through the LeNet,
AlexNet, VGG, ResNet, and EfficientNet architecture families. The topic also
covers augmentation, train/validation discipline, pretrained backbones,
linear probing, fine-tuning, head replacement, top-1/top-5 accuracy,
per-class F1, confusion matrices, and early stopping.

- **P3 (mandatory):** Train a small CNN on CIFAR-10, then compare it with an
  ImageNet-pretrained backbone using fine-tuning and a confusion matrix.

### Topic 3 — CNNs: Object Detection

Extend a classification backbone to localization and variable-output
prediction. The topic covers bounding-box regression, grids, region
proposals, anchors, IoU, label assignment, non-maximum suppression,
precision/recall, AP/mAP, R-CNN through Faster R-CNN, YOLO, SSD, RetinaNet,
anchor-free detection, label formats, and real-time detector settings.

- **P4 (mandatory):** Train a YOLO detector on Pascal VOC 2012, sweep
  confidence and NMS-IoU thresholds, and measure precision/recall and FPS.

### Topic 4 — Recurrent Neural Networks and Sequence Models

Model variable-length sequences and build a sequence-to-sequence translator.
Coverage includes recurrent cells, unrolling and BPTT, vanishing and
exploding gradients, gradient clipping, LSTM and GRU gates, bidirectional and
stacked RNNs, padding/packing/masking, embeddings, encoder-decoder models,
teacher forcing, exposure bias, and the attention concept.

- **P5 (mandatory):** Build an English-to-German encoder-decoder RNN with
  attention on Multi30k and evaluate it with BLEU.
- **P6 (mandatory):** Compare a plain RNN and a BiLSTM for variable-length
  sentiment classification on IMDB reviews.

### Topic 5 — Segmentation and Object Tracking (optional)

Move from boxes to pixels and from per-frame detections to persistent
identities. Coverage includes FCN, U-Net, transposed and dilated convolutions,
DeepLab, instance and panoptic segmentation, Dice/mIoU/mask-AP, Siamese
trackers, Re-ID embeddings, Kalman filtering, Hungarian assignment, SORT,
DeepSORT, MOTA, IDF1, HOTA, and ID switches.

- **P7 (optional):** Train a mini U-Net for semantic segmentation on
  Oxford-IIIT Pet and measure the effect of removing skip connections.
- **P8 (optional):** Combine a detector, Kalman filter, and Hungarian
  assignment on MOT17, comparing ID switches with and without motion.

### Topic 6 — Generative Models (optional)

Understand what different generative families provide: autoencoders,
denoising and anomaly detection, latent structure, VAEs and the
reparameterization trick, ELBO, GANs, diffusion, and flow matching.
Diffusion and flow matching are advanced electives within this topic.

- **P9 (optional):** Upgrade an autoencoder to a VAE to denoise corrupted
  MNIST digits, sample from the latent space, interpolate, and score
  anomalies.
- **P10 (optional advanced elective):** Generate 32×32 images with a small
  diffusion or flow-matching model and compare sample quality and sampling
  cost with the P9 VAE.

### Topic 7 — Knowledge Distillation and Deployment (optional)

Compress and ship a trained model with measurable production behavior.
Coverage includes teacher/student models, dark knowledge, temperature,
Hinton loss, feature and relation-based distillation, self- and
data-free distillation, quantization, pruning, operator fusion, TorchScript,
ONNX, TensorRT, OpenVINO, TFLite, serving patterns, latency percentiles,
throughput, monitoring, drift, and rollback.

- **P11 (optional):** Distill a ResNet-50 teacher into a MobileNetV3 student
  on CIFAR-100 and plot the accuracy-latency Pareto trade-off.
- **P12 (optional):** Export the P4 detector to ONNX, quantize it to INT8,
  and benchmark p95 latency and mAP drift on held-out Pascal VOC frames.

## Repository contents

| File | Description |
| --- | --- |
| [`activation_functions_cnn_study.ipynb`](./activation_functions_cnn_study.ipynb) | Study of activation functions used in neural networks and CNNs |
| [`cnn_cifar100_model_comparison.ipynb`](./cnn_cifar100_model_comparison.ipynb) | CNN implementation, 15-class CIFAR-100 experiment, and comparison of CNN and transformer models |
| [`vgg16_transfer_learning_cifar.ipynb`](./vgg16_transfer_learning_cifar.ipynb) | VGG-16 transfer learning, freezing, fine-tuning, and feature visualization |
| [`From_Introduction_to_Advanced_Deep_Learning_Roadmap.pdf`](./From_Introduction_to_Advanced_Deep_Learning_Roadmap.pdf) | Course roadmap and project specifications |
| [`LICENSE`](./LICENSE) | Custom MIT-style license and usage conditions |

The notebooks currently provide hands-on material focused primarily on Topics
1 and 2, especially CNN classification and transfer learning. The roadmap
defines the complete course scope; additional topic projects can be added as
the course progresses.

## Dataset and experiment setup

The main CNN comparison notebook uses a 15-class subset of CIFAR-100:

- 6,750 training images, 750 validation images, and 1,500 test images
- A custom CNN trained with 32×32 inputs
- Pretrained models trained with 224×224 inputs, except Inception-V3 at
  299×299
- A fixed random seed of 42 for reproducibility
- Custom CNN, ResNet50, EfficientNet-B0, Inception-V3, ViT-Base/16, and
  Swin-Tiny comparisons

The notebook prepares the dataset through the normal torchvision workflow. A
GPU is recommended for pretrained-model experiments, while the custom CNN can
run on a CPU with a smaller configuration.

## Running the lab

### 1. Clone the repository

```bash
git clone https://github.com/codewithdark-git/From-Intro-to-Advanced-DL.git
cd From-Intro-to-Advanced-DL
```

### 2. Install dependencies

```bash
pip install torch torchvision torchaudio
pip install numpy pandas matplotlib seaborn scikit-learn tqdm
pip install notebook
```

Use the [PyTorch installation selector](https://pytorch.org/get-started/locally/)
for a CUDA-specific command.

### 3. Start Jupyter

```bash
jupyter notebook
```

Start with [`cnn_cifar100_model_comparison.ipynb`](./cnn_cifar100_model_comparison.ipynb)
for the main CNN project. Then use
[`vgg16_transfer_learning_cifar.ipynb`](./vgg16_transfer_learning_cifar.ipynb)
for the focused transfer-learning lab. Run cells from top to bottom; the first
run may take time because datasets and pretrained weights must be downloaded.

## Suggested learning workflow

1. Read the explanation before running each section.
2. Record tensor shapes after every major layer.
3. Run the baseline model before changing hyperparameters.
4. Change one variable at a time and record the result.
5. Inspect curves, feature maps, and confusion matrices rather than relying
   only on accuracy.
6. Compare quality, parameter count, training time, latency, and memory use.
7. State the problem, dataset, metrics, and limitations for every project.

## Learning outcomes

After completing the core and selected optional topics, a learner should be
able to:

- Implement and diagnose neural networks, CNNs, and recurrent models.
- Apply transfer learning, object detection, segmentation, and tracking
  techniques.
- Explain the differences between autoencoders, VAEs, GANs, diffusion, and
  flow-matching models.
- Evaluate models with task-appropriate metrics and reproducible experiments.
- Compress, export, benchmark, and monitor a model for deployment.
- Make evidence-based claims about accuracy, efficiency, complexity, and
  failure modes.

## License and usage condition

This repository is available under a **custom MIT-style license**. Before
using this material or learning from it, you must star the
[CNN_lab repository on GitHub](https://github.com/codewithdark-git/CNN_lab).
See [`LICENSE`](./LICENSE) for the complete terms. This custom condition is
part of the license and is not part of the standard OSI MIT License.

If you use this material for learning, cite the original course guidance and
acknowledge this repository. When submitting coursework, write your own
observations and follow your instructor's submission and academic-integrity
requirements.
