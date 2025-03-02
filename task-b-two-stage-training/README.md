
# Task B: Two-Stage Training with Additional Dataset(s)

## Motivation
In medical imaging, obtaining large, labeled datasets is often challenging due to privacy concerns, high annotation costs, and limited availability of expert knowledge. To effectively learn and boost performance on these smaller datasets, we leverage transfer learning techniques which consist of models that are trained on huge amounts of data.

## Goal
Improve the performance of diabetic retinopathy detection using transfer learning by fine-tuning models and understanding the classification results with visualizations and explainable AI.

## Requirements
### b) Two-stage training with additional dataset(s). (5 points)
1. Choose a diabetic retinopathy dataset from either Kaggle DR Resized or APTOS 2019 Blindness Detection (links are provided below).
2. Fine-tune an ImageNet pretrained model (e.g., ResNet18, ResNet34, VGG, EfficientNet, DenseNet) on the selected dataset by unfreezing all pretrained layers. If you have any difficulties, you can also use pretrained weights of Kaggle DR Resized (pretrained_DR_resize) to skip this step: https://www.kaggle.com/competitions/521153S-3005-final-project/data
3. Next up, fine-tune this trained model on the DeepDRiD dataset (keep all the layers unfrozen) and see how it impacts your Cohen Kappa score.
4. Save the fine-tuned model.

The goal of task (b) is to compare the performance of a deep model that is trained and fine-tuned on a task-specific dataset with that of a model that is first trained on a general dataset and then fine-tuned on the same task-specific dataset in task (a).

### Kaggle DR Resized: https://www.kaggle.com/datasets/tanlikesmath/diabetic-retinopathy-resized
### APTOS – 2019: https://www.kaggle.com/datasets/mariaherrerot/aptos2019

## Implementation Details from Report
In this task, we introduced a two-stage training process incorporating an additional dataset, the Kaggle DR Resized dataset, before fine-tuning on DeepDRiD. This methodology aimed to enable the model to initially learn general DR characteristics from a larger, more diverse dataset before specializing on the nuances of the DeepDRiD dataset.

### Results
- **Intermediate Training on Kaggle DR Resized**:
  - Five different pre-trained models (VGG16, ResNet18, ResNet34, DenseNet121, EfficientNet-B0) were trained on the Kaggle DR Resized dataset.
  - The best-performing models were then fine-tuned on the DeepDRiD dataset.
  - During this fine-tuning stage, the backbone layers of the models were frozen, and only the fully connected classification layer was trained.

- **Performance Comparison**:
  - **ResNet34** achieved one of the highest Kappa scores.
  - **EfficientNet-B0** achieved the best Kaggle score of 0.8761.
  - **DenseNet121** attained the highest Kappa score of 0.8714.

This two-stage approach effectively improved feature extraction, allowing for better adaptation to the specific DeepDRiD dataset during the subsequent fine-tuning phase.

