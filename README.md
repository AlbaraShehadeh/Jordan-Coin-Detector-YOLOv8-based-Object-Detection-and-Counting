# Jordan Coins Detection (Tracking & Counting)

## Overview
Jordanian Coins Vision is a computer vision project focused on detecting and recognizing Jordanian coins using YOLOv8, powered by the Roboflow platform. The project aims to achieve accurate real-time object detection and counting of various denominations of Jordanian coins.




## Dataset:
The dataset for this project was created by capturing photos of Jordanian coins and then uploading them to the Roboflow platform. [dataset](https://universe.roboflow.com/coinsvision/jordan-coins-detection-nqdbs/dataset/1)


### Data Collection:

The dataset consists of images with the following 9 classes:

- 5-Piastres
- 10-Piastres
- 1-4-dinar
- 1-2-dinar
- 1-dinar
- 5-dinars
- 10-dinar
- 20-dinar
- 50-dinar

<div style="display: flex; flex-direction: column; justify-content: space-between;">
  <img src="examples/example_1.jpg" alt="Example Annotated Image 1" width="300"/>
  <img src="examples/example_2.jpg" alt="Example Annotated Image 2" width="300"/>
</div>

<div style="display: flex; flex-direction: column; justify-content: space-between;">
  <img src="examples/example_3.jpg" alt="Example Annotated Image 3" width="300"/>
  <img src="examples/example_4.jpg" alt="Example Annotated Image 4" width="300"/>
</div>




### Data Annotation:
Roboflow was used for annotation, making the dataset ready for training the YOLOv8 model.

Example Annotated Images:

<div style="display: flex; flex-direction: column; justify-content: space-between;">
  <img src="examples/annotated/1.png" alt="Example Annotated Image 1" width="300"/>
  <img src="examples/annotated/2.png" alt="Example Annotated Image 2" width="300"/>
</div>

### Data Augmentation

To enhance the diversity and robustness of our dataset, we applied the following augmentations during the training process:

- **Flip:** Horizontal and Vertical
- **Crop:** Minimum Zoom of 0%, Maximum Zoom of 20%
- **Rotation:** Random rotation between -15° and +15°
- **Hue:** Random adjustment between -15° and +15°
- **Exposure:** Random adjustment between -10% and +10%

By utilizing these augmentation techniques, each training example was transformed into multiple variations, exposing the model to a broader range of scenarios. This contributed to improved performance and generalization during the object detection and counting tasks.



## Training
The YOLOv8 model was trained on the annotated dataset using the Roboflow platform. The training process involved optimizing the model to accurately detect and classify the various denominations of Jordanian coins.

