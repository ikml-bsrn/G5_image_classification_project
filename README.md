# WiSAR: Image Classification for Wilderness Search and Rescue (2025)

## Overview
This project investigates the effectiveness of YOLOv5, YOLOv8, and YOLOv11 models in detecting persons in Wilderness Search and Rescue (WiSAR) scenarios using both RGB and thermal infrared (IR) imagery. The aim is to evaluate model performance across detection accuracy, inference speed, and generalization capability in natural, occluded environments.

## Background
WiSAR missions face obstacles such as dense vegetation, lighting variability, and environmental occlusion, which reduce the effectiveness of manual search efforts. Deep learning methods like YOLO have shown potential for automating person detection. Leveraging both RGB and IR data can enhance detection under varied conditions (e.g., daylight and low visibility). This project focuses on the WiSARD dataset, which contains labeled RGB and thermal image pairs specific to SAR contexts.

## Methodology

We evaluated YOLOv5, YOLOv8, and YOLOv11 for human detection in wilderness search and rescue (WiSAR) using the WiSARD dataset. Each model was trained and tested separately on RGB and thermal IR image subsets, selected from the “MtErie” and “FHL” locations. A 60-20-20 split was applied within each folder, and default YOLO data augmentation was enabled. Training was conducted in Google Colab with manual hyperparameter tuning (batch size, learning rate), using Ultralytics' implementation and custom YAML configuration for single-class detection.

- YOLOv5: Baseline model widely used in SAR literature and the WiSARD paper.
- YOLOv8: Balanced in terms of speed, accuracy, and hardware efficiency.
- YOLOv11: Recent architecture shown to handle occlusion and difficult detection scenarios effectively.
- Older or less-documented versions (e.g., YOLOv6, v7, v9, v10) were excluded due to inconsistent results or poor SAR relevance.

## Dataset
We used the **WiSARD** dataset, a multimodal collection of over 70,000 RGB and thermal infrared images captured via UAVs in wilderness environments. For this project, we selected images from the MtErie and FHL locations based on criteria including human presence, occlusion, and alignment of RGB–IR pairs. Only labeled images were included. The dataset was split 60-20-20 (train/val/test) per folder to ensure environment diversity and mitigate aggregation bias.

Refer to the link below for more information about the WiSARD Dataset:
https://sites.google.com/uw.edu/wisard/

## Model Development

- Data preprocessing: Image resizing, normalisation, and formatting into YOLO-compliant annotations.
- Thermal-visual separation: Models were trained separately on RGB and IR subsets to compare modality performance.
- Training & tuning: Uniform hyperparameters were applied initially; adjustments were made based on results and resource constraints.
- Evaluation: Recall, precision, and mAP were used as performance metrics.
- Ethical Considerations

We used the FATES framework to evaluate ethical issues around dataset bias, human subject visibility, and transparency in model reporting.

## Results

- Thermal IR consistently outperformed RGB across all metrics and YOLO versions.
- YOLOv11 with thermal IR achieved the highest recall (0.592).
- YOLOv11 was the top performer in both RGB and IR modalities.
- Manual hyperparameter tuning improved stability across models.
- Aggregation bias was identified and mitigated by ensuring folder-level distribution in train/val/test sets.

All training logs, configuration files, and visualisations are included in the /results and /configs directories.


## The Team

- **Ikmal Basirun (Project Manager)**: Led planning, coordination, team meetings, dataset aggregation and review, model development.
- **Amira Faisal**: Led background research and literature review, contributed to dataset review, designed project poster.
- **Zahra Husain**: Contributed to literature review and dataset evaluation.
- **Thomas Reeve**: Supported literature review, data aggregation, and model development.
- **Faisal Alharbi**: Focused on hyperparameter tuning research, assisted in model development.
- **Syahmina Mohd Ansar**: Contributed to ethical considerations (FATES) and supported documentation.


