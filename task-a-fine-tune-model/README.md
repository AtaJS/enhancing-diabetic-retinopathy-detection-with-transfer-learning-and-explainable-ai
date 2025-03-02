
# Task A: Fine-tune a Pretrained Model using the DeepDRiD Dataset

## Motivation
In medical imaging, obtaining large, labeled datasets is often challenging due to privacy concerns, high annotation costs, and limited availability of expert knowledge. To effectively learn and boost performance on these smaller datasets, we leverage transfer learning techniques which consist of models that are trained on huge amounts of data.

## Goal
Improve the performance of diabetic retinopathy detection using transfer learning by fine-tuning models and understanding the classification results with visualizations and explainable AI.

## Requirements
### a) Fine-tune a pretrained model using the DeepDRiD dataset. (5 points)
1. Download the DeepDRiD dataset from the provided link along with the template code which provides an explanation on diabetic retinopathy and the dataset itself. All the images for training, validation, and evaluation are 512 by 512 in size.
2. Fine-tune an ImageNet pretrained model (e.g., ResNet18, ResNet34, VGG, EfficientNet, DenseNet) on the DeepDRiD dataset. Evaluate and test it on the validation and test sets. Your goal here is to reach the highest Cohen Kappa score you can get.
3. Experiment with different image augmentation techniques and check whether they boost your evaluation metrics or decrease them.
4. Save the fine-tuned model.

The goal of task (a) is to see how a model that is trained on a general dataset (pretrained) works for a specific task.

## Reference Architecture
Here are two reference architectures described in the template code:
- **Single Image Architecture**: Processes each image separately.
- **Dual Image Architecture**: Takes two images of the same eye to fuse their features during training and evaluation.

You can pick one or try both for tasks (a)-(e).

## Implementation Details from Report
In this task, we fine-tuned a ResNet18 model pretrained on ImageNet for the classification of diabetic retinopathy severity levels using the DeepDRiD dataset. The process was executed in two distinct stages:
1. **Initial Fine-Tuning with Frozen Backbone**: The feature extraction layers of the pre-trained ResNet18 model were frozen, and only the fully connected classification head was trained using the DeepDRiD data.
2. **Full Fine-Tuning by Unfreezing Layers**: All layers of the ResNet18 model were unfrozen, allowing the entire network to be trained on the DeepDRiD dataset.

### Results
- **Initial Fine-Tuning**:
  - Training Kappa Score: 0.6284
  - Training Accuracy: 51.17%
  - Best Validation Kappa: 0.6619 at epoch 18
  - Validation Accuracy: 55.00%
  - Kaggle Submission Score: 0.6800

- **Full Fine-Tuning**:
  - Training Kappa Score: 0.7721
  - Training Accuracy: 57.92%
  - Best Validation Kappa: 0.7633 at epoch 6
  - Validation Accuracy: 63.25%
  - Kaggle Submission Score: 0.7092

These results indicated that while fine-tuning enhanced the model’s performance, challenges related to class imbalance persisted, particularly for the accurate identification of severe DR cases.

