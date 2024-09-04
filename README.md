# Robust object detection in extreme construction conditions

[Paper](https://www.sciencedirect.com/science/article/pii/S0926580524002231) | [Dataset](#dataset) | [Citation](#citation)

## Introduction
Current construction object detection models are vulnerable in complex conditions, as they are trained on conventional data and lack robustness in extreme situations. The lack of extreme data with relevant annotations worsens this situation. A new end-to-end unified image adaptation You-Only-Look-Once-v5 (UIA-YOLOv5) model is presented for robust object detection in five extreme conditions: low/intense light, fog, dust, and rain. The UIA-YOLOv5 adaptively enhances the input image to make image content visually clear and then feeds the enhanced image to the YOLOv5 for object detection. Sufficient extreme images are synthesized via the neural style transfer (NST) and mixed with conventional data for model training to reduce domain shift. An extreme construction dataset (ExtCon) containing 506 images labeled with 13 objects is constructed for real-world evaluation. Results show that the UIA-YOLOv5 keeps the same performance as the YOLOv5 on conventional data but is more robust to extreme data with an 8.21% mAP_05 improvement.

## Method
Figure 1 is the overall framework of the proposed method. In the training phase, conventional images are first stylized via an arbitrary NST model to simulate extreme conditions. Mixing the stylized and conventional images for model training is achieved by applying different stylization strengths. Then, the input image is enhanced adaptively through the UIA module to eliminate the extreme condition-related information before being fed into the YOLOv5 model. Two output pipelines are produced after the UIA module: one is used to calculate the image restoration (Res.) loss, and the other is used as the input of the YOLOv5 model for object detection to obtain the detection (Det.) loss. Finally, the trainable weights of the UIA and YOLOv5 are optimized jointly according to the joint loss in each training epoch. The proposed UIA-YOLOv5 model is still an end-to-end/one-stage model like the original one, i.e., the UIA and YOLOv5 perform as a whole during both training and application phases.

![image](https://github.com/user-attachments/assets/24854c4a-8f7e-4860-bb65-f9e0e08f451d)

Figure 1. UIA-YOLOv5 framework.



## Dataset
The **ExtCon** is an extreme real-world construction image dataset, labeled with 13 construction moving objects: **Worker**, **Tower crane**, **Hanging hook**, **Vehicle/Mobile crane**, **Roller**, **Bulldozer**, **Excavator**, **Truck**, **Loader**, **Pump truck**, **Concrete mixer**, **Pile driver**, and **Other vehicle**.
![image](https://github.com/dyxm/ExtCon/assets/17799440/a67ad06d-07f4-45ca-a7c1-77282d6eff8d)

The **ExtCon** can be accessed:
- at the [TeraBox](https://terabox.com/s/1I7THz2RfGos_XxSLgqI7RQ).
- or, at the [Baidu Netdisk](https://pan.baidu.com/s/14slF01E78bWIAyoUpUPQvQ) using the code: **wszd**

## Citation
Please cite our work if you find the dataset useful.
```
@article{DING2024105487,
  title = {Robust object detection in extreme construction conditions},
  journal = {Automation in Construction},
  volume = {165},
  pages = {105487},
  year = {2024},
  issn = {0926-5805},
  doi = {https://doi.org/10.1016/j.autcon.2024.105487},
  author = {Yuexiong Ding and Ming Zhang and Jia Pan and Jinxing Hu and Xiaowei Luo},
}
```
