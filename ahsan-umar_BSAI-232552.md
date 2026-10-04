# CNN Lab Observations

## Experiment

This is from the 15-class CIFAR-100 Classification problem.

Ahsan Umar (BSAI-232552) · on notebook run, `experiment_log.json` and `model_comparison.csv` - one run with seed 42 reference model on GPU.

## Setup

First 15 CIFAR-100 classes, 6,750 train / 750 val / 1,500 test images (100 per class in test). The custom CNN was trained at 32×32 and for as many as 20 epochs. Up to 8 epochs for the five pre-trained models at 224×224 (299×299 - for Inception).

| Model | Acc (%) | F1 (%) | Params (M) | Train time (s) |
|:---|---:|---:|---:|---:|
| Custom CNN | 70.07 | 69.52 | 0.82 | 176 |
| ResNet50 | 93.73 | 93.72 | 23.54 | 1049 |
| EfficientNet-B0 | 94.00 | 93.98 | 4.03 | 692 |
| Inception-V3 | 93.07 | 93.06 | 24.39 | 1569 |
| ViT-Base/16 | 95.40 | 95.38 | 85.81 | 2286 |
| Swin-Tiny | 93.27 | 93.28 | 27.53 | 864 |

## What I Noticed

1. **Pretraining matters most.** The CNN built from scratch is 23-25 points behind all pretrained CNNs. Also it is not overfitting, its training error (evaluate_accuracy/) is higher than the test one, and the curves grow when the 20 epochs expire.

2. The pretrained models are near neighbors. There is only a 2.3 point difference. The mean (+-~0.6 points) is ~1.5 points when testing on 1,500 test images, between ResNet50, EfficientNet-B0, Inception and Swin compete for the first place. One of the only gaps I would be willing to take the risk on is the lead of ViT, and it's only one seed at a time.

3. The optimal middle-ground is 3. It gets 94.0% with 4M parameters in 692 s. The added advantage of ViT is that for the same dimension of parameters it gains 21× points and for the same dimension of forward training it gains 3.3 × points. The TV CNN and the most basic of the pretrained CNN is Inception and that's really partly because of the larger input size of 299 px, but also partially because it has the lowest CNN.The TV CNN and lowest of the pretrained is Inception, partly because of the larger input size of 299 px, but also partly because it is the lowest CNN.

4. The early stopping is used to choose early weights. The code uses the lowest checkpoint with a validation loss. Although the accuracy when validating Swin was 94.0% at epoch 5, it was epoch 1 for the network. Both ResNet50 and Inception were found to be on epoch 3. They may have suffered a slight disadvantage for stopping on loss or not stopping on accuracy which may explain their ranking.

5. After epoch 3 ResNet50's training loss was 0.013 and the loss was approximately 0.19 or 0.22 for its validation.At epoch 3 overfitting was seen differently for ResNet50 where training loss was 0.013 and Validation loss was around 0.19 or 0.22. The training accuracy rate for ViT was perfect, but test (validation) loss was still declining towards the end. The curves for EfficientNet-B0 were the smoothest and the gap between training and testing was the smallest (+3.5 points as opposed to +4.6 points to +6.6 points for the rest). These gaps are approximate because the accuracy is stored and averaged across each epoch that the augmentation is on.

6. Baby vs boy is the most common error for all five pretrained models (ResNet50 22 babies were misclassified as boy, while 15 babies were misclassified as boy in the ViT model). The next two are Bear vs beaver, where 15 bears are delivered to beaver from EfficientNet-B0. The same custom CNN also confuses babies from the bee/beetle/butterfly type of group (about 10 each type) and sent 30 babies to boy. The notations of a bowl/bottle and apple/beetle are not present in the matrices as part of the discussion as specified in the notebook.
