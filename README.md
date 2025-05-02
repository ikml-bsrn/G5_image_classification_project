# WiSAR: Image Classification for Wilderness Search and Rescue

## Overview
This project investigates the effectiveness of YOLOv5, YOLOv8, and YOLOv11 models in detecting persons in Wilderness Search and Rescue (WiSAR) scenarios using both RGB and thermal infrared (IR) imagery. The aim is to evaluate model performance across detection accuracy, inference speed, and generalization capability in natural, occluded environments.

## Background
WiSAR missions face obstacles such as dense vegetation, lighting variability, and environmental occlusion, which reduce the effectiveness of manual search efforts. Deep learning methods like YOLO have shown potential for automating person detection. Leveraging both RGB and IR data can enhance detection under varied conditions (e.g., daylight and low visibility). This project focuses on the WiSARD dataset, which contains labeled RGB and thermal image pairs specific to SAR contexts.

## Methodology
Model Selection

We selected YOLOv5, YOLOv8, and YOLOv11 based on literature benchmarks, performance consistency, and relevance to SAR applications:

- YOLOv5: Baseline model widely used in SAR literature and the WiSARD paper.
- YOLOv8: Balanced in terms of speed, accuracy, and hardware efficiency.
- YOLOv11: Recent architecture shown to handle occlusion and difficult detection scenarios effectively.
- Older or less-documented versions (e.g., YOLOv6, v7, v9, v10) were excluded due to inconsistent results or poor SAR relevance.

## Dataset

We used only the WiSARD dataset for its SAR-specific relevance and inclusion of paired RGB and thermal IR images. Images were manually reviewed, and only high-quality pairs with clear person labels were retained. We split the dataset into:

- 472 images for training
- 113 images for validation
- 142 images for testing
- Each subset was selected to minimize overlap in environmental context, though a later error revealed that the test set had domain shift (Environment 3 only), which affected model generalisation.

## Model Development

- Data preprocessing: Image resizing, normalisation, and formatting into YOLO-compliant annotations.
- Thermal-visual separation: Models were trained separately on RGB and IR subsets to compare modality performance.
- Training & tuning: Uniform hyperparameters were applied initially; adjustments were made based on results and resource constraints.
- Evaluation: Recall, precision, and mAP were used as performance metrics.
- Ethical Considerations

We used the FATES framework to evaluate ethical issues around dataset bias, human subject visibility, and transparency in model reporting.

## Results (Preliminary)

Initial model showed a recall score of 0.48. Howeveer, when validated using the testing set, recall score reduced to ~0.11, which largely is due to spatial domain mismatch in training vs. test environments. This is currently being fixed.

Final evaluation and benchmarking are in progress.

## The Team

- **Ikmal Basirun (Project Manager)**: Led planning, coordination, team meetings, dataset aggregation and review, model development.
- **Amira Faisal**: Led background research and literature review, contributed to dataset review, designed project poster.
- **Zahra Husain**: Contributed to literature review and dataset evaluation.
- **Thomas Reeve**: Supported literature review, data aggregation, and model development.
- **Faisal Alharbi**: Focused on hyperparameter tuning research, assisted in model development.
- **Syahmina Mohd Ansar**: Contributed to ethical considerations (FATES) and supported documentation.


