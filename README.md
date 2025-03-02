# Enhancing Diabetic Retinopathy Detection via Transfer Learning and Model Optimization

## Project Overview
This project aims to enhance the performance of diabetic retinopathy (DR) detection using transfer learning and fine-tuning methodologies. The primary objective is to develop robust deep learning models capable of accurately classifying DR severity levels, leveraging pre-trained models and various optimization techniques. The project systematically explores five key tasks designed to optimize the model and evaluate its performance comprehensively.

## Key Terminologies
- **Fine-tuning**: The process of taking a pre-trained model and further training it on a specific dataset to boost performance. This may include unfreezing one or more layers of the pre-trained model.
- **Augmentations**: Transformations applied to the training data to increase the diversity of samples and improve model generalization. Common techniques include rotations, flips, color adjustments, and cropping.
- **Kaggle**: A community platform for data science and machine learning competitions and datasets.
- **Cohen Kappa Score**: A statistical measure of inter-rater reliability used to assess the agreement between two raters (or models) when assigning categorical labels to data points.
- **Explainable AI**: Techniques that make the AI decision-making process more interpretable and explainable to humans.
- **GradCAM**: Gradient-weighted Class Activation Mapping, a technique used to visualize which parts of an image contribute the most to a model's prediction.
- **Attention**: Mechanisms that allow the model to focus on specific regions of an input image that are most relevant to the task at hand.
- **Ensemble Learning**: Combining multiple models to improve predictive performance, reduce overfitting, and increase model robustness.
- **Image Pre-processing**: Steps taken to prepare images for input into a machine learning model, such as resizing, normalization, and augmentation.

## Diabetic Retinopathy Grading
### Diabetic Retinopathy
Diabetic Retinopathy is a complication of diabetes that affects the retina. High blood sugar levels damage blood vessels, leading to swelling of the retinal tissue and blurry vision. In severe cases, it can cause permanent blindness.

### Key Terms
- **Fundus Images**: Pictures of the back part of the eye, including the retina.
- **Hemorrhages**: Areas where blood vessels have leaked or burst, creating small blood spots.
- **Fovea**: The darker pit in the retina responsible for sharp vision.
- **Macula**: The small circular region around the fovea responsible for central vision.
- **Soft Exudates / Cotton Wool Spots**: Fluffy white patches on the retina caused by tiny areas of damage.
- **Hard Exudates**: Yellowish deposits of fats and proteins that leak from blood vessels.
- **Optic Disc**: The brighter region where the optic nerve connects to the retina.
- **Aneurysm**: Small, balloon-like bulges in weakened blood vessels that can leak fluid or blood into the retina.

### Classification
- **Non-Proliferative Diabetic Retinopathy (NPDR)**
  - **Mild NPDR**: Presence of microaneurysms.
  - **Moderate NPDR**: Increased number of microaneurysms and dot hemorrhages, appearance of hard exudates, and mild macula edema.
- **Proliferative Diabetic Retinopathy (PDR)**
  - Growth of abnormal new blood vessels on the retinal surface, significantly increasing the risk of vision loss.

## DeepDRiD Dataset
The DeepDRiD (Diabetic Retinopathy Image Dataset) is a comprehensive dataset designed to aid in the diagnosis and grading of diabetic retinopathy. It includes 2,000 images from patients with diverse backgrounds, taken under different camera angles and lighting conditions. Each patient has four images in total, two of their left eyes and two for the right eye.

### Dataset Features
- **patient_id**: Patients with the serial number.
- **image_id**: Image sequence number.
- **patient_DR_Level**:
  - 0: No apparent retinopathy
  - 1: Mild – NPDR
  - 2: Moderate – NPDR
  - 3: Severe – NPDR
  - 4: PDR
  - 5: Both eye fundus images are low quality and cannot be diagnosed and graded.

## Tasks and Implementation
### Task A: Fine-tune a Pretrained Model using the DeepDRiD Dataset
- **Goal**: Improve DR detection performance using transfer learning.
- **Implementation**: Fine-tune a ResNet18 model pretrained on ImageNet for DR classification using the DeepDRiD dataset.
- **Results**: Enhanced model performance with challenges related to class imbalance.

### Task B: Two-Stage Training with Additional Dataset(s)
- **Goal**: Compare performance of models trained on general vs. task-specific datasets.
- **Implementation**: Two-stage training process incorporating the Kaggle DR Resized dataset before fine-tuning on DeepDRiD.
- **Results**: Improved feature extraction and adaptation to the DeepDRiD dataset.

### Task C: Incorporate Attention Mechanisms in the Model
- **Goal**: Enhance model's ability to prioritize critical regions within retinal images.
- **Implementation**: Integrate attention mechanisms (Channel Attention, Spatial Attention, Self-Attention) into the model.
- **Results**: Attention mechanisms aided feature learning but did not surpass Task B performance.

### Task D: Compare the Performance of Different Models and Strategies
- **Goal**: Perform ensemble learning and apply multiple preprocessing techniques.
- **Implementation**: Ensemble learning techniques (Stacking, Boosting, Weighted Average, Max Voting, Bagging) and image preprocessing techniques (Ben Graham, Circle Cropping, CLAHE, Gaussian Blur, Sharpening).
- **Results**: Ensemble methods alone were insufficient to overcome class imbalances.

### Task E: Creating Visualizations and Explainable AI
- **Goal**: Visualize model performance and understand decision-making through Explainable AI.
- **Implementation**: Visualizations (scatter plots, line graphs) for losses and accuracies, GradCAM for feature analysis.
- **Results**: Insights into model behavior and training instabilities.

## References
- What is Diabetic Retinopathy https://www.aao.org/eye-health/diseases/what-is-diabetic-retinopathy
- Fundus Image Reference https://www.themedicaleyecenter.com/diabetic-eye-disease-management-manchester/
- General Information on DR https://www.nei.nih.gov/learn-about-eye-health/eye-conditions-and-diseases/diabetic-retinopathy
- More Information on DR https://www.mayoclinic.org/diseases-conditions/diabetic-retinopathy/symptoms-causes/syc-20371611
- DeepDRiD Challenge https://www.sciencedirect.com/science/article/pii/S2666389922001040
- What is Fine-tuning? https://www.techtarget.com/searchenterpriseai/definition/fine-tuning
- PyTorch Augmentations https://anushsom.medium.com/image-augmentation-for-creating-datasets-using-pytorch-for-dummies-by-a-dummy-a7c2b08c5bcb
- Kaggle https://www.kaggle.com/
- Cohen’s Kappa Explanation https://datatab.net/tutorial/cohens-kappa
- Explainable AI (XAI) https://builtin.com/artificial-intelligence/explainable-ai
- GradCAM Article https://datascientest.com/en/what-is-the-grad-cam-method
- Ensemble Learning and Techniques https://www.geeksforgeeks.org/a-comprehensive-guide-to-ensemble-learning/
