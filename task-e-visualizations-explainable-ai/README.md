
# Task E: Creating Visualizations and Explainable AI

## Motivation
In medical imaging, obtaining large, labeled datasets is often challenging due to privacy concerns, high annotation costs, and limited availability of expert knowledge. To effectively learn and boost performance on these smaller datasets, we leverage transfer learning techniques which consist of models that are trained on huge amounts of data.

## Goal
Improve the performance of diabetic retinopathy detection using transfer learning by fine-tuning models and understanding the classification results with visualizations and explainable AI.

## Requirements
### e) Creating Visualizations and Explainable AI (5 points)
- Implement visualizations (e.g., scatter plots and line graphs) for your models' losses and accuracies on training and validation datasets to analyze the convergence and overall performance of the model.
- Use Explainable AI techniques such as GradCAM to analyze what features in the image are contributing the most and the least in the model's decision-making process. Please also include a few visualization results in the report.
- The goal of task (e) is to visualize the performance of the model by creating graphs and understanding the model's decision making through explainable AI.

## Implementation Details from Report
In this task, we focused on visualizing the performance of the model and understanding its decision-making process through Explainable AI techniques.

### Visualizations
- **Scatter Plots and Line Graphs**: Created for models' losses and accuracies on training and validation datasets to analyze the convergence and overall performance of the model.
- **Loss and Accuracy Trends**: Plots were generated to highlight training instabilities and areas for potential improvement.

### Explainable AI Techniques
- **GradCAM (Gradient-weighted Class Activation Mapping)**: Used to analyze what features in the image are contributing the most and the least in the model's decision-making process.
  - The Grad-CAM analysis indicated that the models primarily focus on the optic disc and surrounding areas, which aligns with medical knowledge about DR diagnosis.
  - Visualization results were included in the report to provide insights into model behavior.

## Results
The visualization and XAI analysis provided insights into model behavior, revealing areas of focus and potential training instabilities. The Grad-CAM analysis indicated that the models primarily focus on the optic disc and surrounding areas, which aligns with medical knowledge about DR diagnosis. The loss and accuracy plots highlighted training instabilities that could be addressed through techniques like learning rate scheduling and batch normalization.

## References for Task (e)
- Ben Graham’s Preprocessing
- Circular Cropping
- CLAHE
- Different Types of Blurs
- Ensemble Learning and Types
- More Ensemble Types
