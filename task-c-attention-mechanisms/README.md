
# Task C: Incorporate Attention Mechanisms in the Model

## Motivation
In medical imaging, obtaining large, labeled datasets is often challenging due to privacy concerns, high annotation costs, and limited availability of expert knowledge. To effectively learn and boost performance on these smaller datasets, we leverage transfer learning techniques which consist of models that are trained on huge amounts of data.

## Goal
Improve the performance of diabetic retinopathy detection using transfer learning by fine-tuning models and understanding the classification results with visualizations and explainable AI.

## Requirements
### c) Incorporate attention mechanisms in the model. (10 points)
1. Implement attention mechanisms (e.g., self-attention, channel attention, or spatial attention) in your DeepDRiD model architecture.
2. Evaluate the impact of attention mechanisms on model performance.

The goal of task (c) is to apply and see how attention is affecting the model and its performance.

## Implementation Details from Report
In this task, we focused on enhancing the model’s ability to prioritize critical regions within retinal images by integrating attention mechanisms. Traditional convolutional neural networks often treat all image features with equal importance. However, attention-based models can prioritize the most relevant features, potentially leading to improved diabetic retinopathy (DR) detection accuracy.

### Attention Mechanisms Explored
- **Channel Attention**: Specifically the Squeeze-and-Excitation (SE) Block, which highlights important features across different convolutional filters.
- **Spatial Attention**: Enables the model to focus on specific retinal areas affected by DR.
- **Self-Attention**: Inspired by Transformer architectures, captures long-range dependencies within the image.

### Results
The modified model incorporating these attention mechanisms was trained using the same two-stage setup as in Task B to ensure a fair comparison. The best-performing model from Task B (DenseNet121) served as the baseline.

- **Performance Comparison**:
  - The Kappa score experienced a slight decrease, from 0.8714 to 0.7992.
  - Validation accuracy dropped from 70.00% to 60.25%.
  - Kaggle score decreased from 0.8761 to 0.8106.

These results suggest that while attention mechanisms aided the model in learning important retinal features, the overall performance did not surpass that of Task B. This indicates that the implemented attention mechanisms, in isolation, might not be sufficient without further optimization and tuning.

