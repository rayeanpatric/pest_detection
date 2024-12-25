# Analysis of YOLO Family in Pest Detection

This repository contains the implementation of a pest detection system using YOLO-based object detection models. The project aims to optimize and deploy models for real-time pest detection in precision agriculture, enhancing agricultural productivity and sustainability.

## Overview

This repo evaluates four YOLO variants—YOLOv8, YOLOv9, YOLOv10, and YOLOv11—on their performance in detecting agricultural pests. Key metrics such as precision, recall, F1-score, accuracy, and mean Average Precision (mAP@0.5) were assessed using the NBAIR dataset, containing 40 pest species. The system is designed for deployment on resource-constrained environments like Jetson devices.

## Key Results

- **Best Performing Model**: YOLOv9 achieved the best overall performance with:
  - Accuracy: 93%
  - mAP@0.5: 0.959
  - F1-score: 0.96
  
- **Other Highlights**:
  - YOLOv11: Highest precision (0.932).
  - YOLOv10: Efficient latency and competitive detection capabilities, especially on mobile devices.
  - YOLOv8: Underperformed compared to others but has optimization potential.

## Dataset

The **National Bureau of Agricultural Insect Resources (NBAIR)** dataset was used, which includes [3,981 images](Dataset/) representing five common pest species:

| S. No | Insect Name          | No. of Samples | No. of Test Samples |
|-------|----------------------|----------------|----------------------|
| 1     | Asian Lady Beetle    | 876            | 300                  |
| 2     | Ladybug              | 503            | 300                  |
| 3     | Mealy Bug            | 802            | 300                  |
| 4     | Pyrilla perpusilla   | 1099           | 300                  |
| 5     | Stink Bug            | 701            | 300                  |
| **Total** | **-**             | **3981**       | **1500**            |

Data augmentation techniques were applied to balance the dataset and improve robustness.

## Models Evaluated

### YOLOv8
- Features: Hierarchical feature extraction, multi-scale detection.
- Limitations: Struggles with false positives, lower accuracy (77.5%).

### YOLOv9
- Features: Reversible functions, advanced gradient management, RepConv blocks.
- Strengths: Best accuracy (93%) and mAP@0.5 (0.959).

### YOLOv10
- Features: Dual-head detection system, Partial Self-Attention (PSA) module.
- Strengths: Low latency, mobile optimization.

### YOLOv11
- Features: C3K2 block, SPFF module, C2PSA block.
- Strengths: High precision (0.932), multi-scale prediction.

 All the model files are at the [Model Folder](Models/) in this repo.


## Data Augmentation Techniques

- **Grayscale Conversion**: Focused on texture and structure.
- **Zoom and Rotation**: Enhanced object recognition at various angles.
- **Color Variations and Blurring**: Improved generalization across environments.
- **Mixup Augmentation**: Combined two images to introduce label diversity.
- **RandAugment**: Applied random transformations like rotation, shear, and color modification.

## Results Summary

All the result metrics are and graphs are at [Results Folder](Results/)
| Metrics         | YOLOv8 | YOLOv9 | YOLOv10 | YOLOv11 |
|-----------------|--------|--------|---------|---------|
| Precision       | 0.687  | 0.834  | 0.759   | 0.932   |
| F1-Score        | 0.81   | 0.96   | 0.94    | 0.95    |
| Recall          | 0.78   | 1.0    | 1.0     | 1.0     |
| mAP@0.5         | 0.822  | 0.959  | 0.951   | 0.952   |
| Accuracy        | 77.5%  | 93%    | 85%     | 89.1%   |

### Configuration

Each model was trained with the following hyperparameters:

- **Batch Size**: 16
- **Epochs**: 50
- **Learning Rate**: 0.001
- **Input Size**: 640x640 pixels

## System Architecture

The models were optimized using TensorRT for deployment on NVIDIA Jetson devices, ensuring real-time pest detection with minimal computational overhead.

### Conclusion

- YOLOv9 is the most balanced model for real-time pest detection, excelling in accuracy and mAP.
- YOLOv11 offers superior precision but at the cost of efficiency.
- YOLOv10 is ideal for latency-sensitive mobile applications.
- Future research will focus on improving latency, reducing false positives, and enhancing robustness under various environmental conditions.

## Authors

- Rayean Patric
- Dharun Raagav

**Affiliation:** SRM Institute of Science and Technology Tiruchirappalli, Tamil Nadu, India.

---

## License

This project is open-source and released under the [MIT License](LICENSE).

---

Feel free to tweak the times or the buzzer frequency to suit your needs! Let me know if you need further clarification or assistance.


