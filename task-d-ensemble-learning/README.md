
# Task D: Compare the Performance of Different Models and Strategies

## Motivation
In medical imaging, obtaining large, labeled datasets is often challenging due to privacy concerns, high annotation costs, and limited availability of expert knowledge. To effectively learn and boost performance on these smaller datasets, we leverage transfer learning techniques which consist of models that are trained on huge amounts of data.

## Goal
Improve the performance of diabetic retinopathy detection using transfer learning by fine-tuning models and understanding the classification results with visualizations and explainable AI.

## Requirements
### d) Compare the performance of different models and strategies. (20 points)
1. Use at least three transfer models that you've trained using task (b) and perform ensemble learning. Try out the following ensemble techniques (Stacking, Boosting, Weighted Average, Max Voting, Bagging) and analyze whether the performance increases or not.
2. Try out different image preprocessing techniques such as Ben Graham, Circle Cropping, CLAHE, adding gaussian blur, sharpening up the images etc.

The goal of task (d) is to perform ensemble learning by training various models and combining their predictions and analyzing whether it boosts the performance. Along with that, applying multiple preprocessing techniques to see if that has any effect on the model.

## Implementation Details from Report
In this task, we explored the application of ensemble learning techniques to further enhance classification performance. Recognizing that individual models possess unique strengths and weaknesses, ensemble learning aims to combine the predictions of multiple models to produce a more robust and accurate final prediction.

### Ensemble Learning Techniques Explored
- **Majority Voting**: Each model casts a vote for a class, and the class with the most votes is selected as the final prediction.
- **Weighted Averaging**: Predictions from different models are combined based on their individual performance.
- **Bagging**: Decision trees trained on different subsets of the predictions.
- **Boosting**: A sequential training approach where each subsequent model attempts to correct the errors of its predecessors.
- **Stacking**: A more complex meta-learning technique where a learner is trained on the outputs of multiple base models to generate improved predictions.

### Results
Initial attempts at ensemble learning yielded poor classification scores when tested on the Kaggle platform. The predictions exhibited significant bias, with some ensemble methods predicting only a single class for all test samples. Further analysis revealed that the root cause of this issue was the inherent class imbalance within the training dataset.

To mitigate this issue, a SoftMax function was applied to the model outputs to convert the raw logits into probability distributions. This adjustment aimed to improve prediction diversity and partially address the imbalance problem. While the application of SoftMax provided some improvement, it did not fully resolve the class imbalance issue. Some ensemble methods continued to show a bias towards the overrepresented classes.

These results demonstrated that ensemble methods alone are insufficient to overcome severe class imbalances. A more fundamental solution requires addressing the imbalance at the training stage itself, potentially through the implementation of class weighting in the loss function to ensure all classes are learned effectively.

### Image Preprocessing Techniques Explored
- **Ben Graham**: A preprocessing technique that involves resizing images while maintaining aspect ratio.
- **Circle Cropping**: Cropping images into circular shapes to focus on relevant regions.
- **CLAHE (Contrast Limited Adaptive Histogram Equalization)**: Enhancing contrast in images.
- **Gaussian Blur**: Applying a Gaussian blur filter to smooth images.
- **Sharpening**: Enhancing edges in images to make them appear sharper.

