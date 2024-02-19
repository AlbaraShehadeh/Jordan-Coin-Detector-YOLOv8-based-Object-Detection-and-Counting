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


### Preprocessing :
Preprocessing ensures the dataset is in a standard format (e.g. all images are the same size). This step is essential to ensure the dataset is consistent before training a model.
Preprocessing applies to all images in the Train, Valid, and Test set (unlike Augmentations, which only apply to the Train set).

We used Auto-Orient and Resize to standardize dimensions.
Auto-Orient: Auto-orient strips your images of their EXIF data so that you see images displayed the same way they are stored on disk. 
Resize changes your image size and, optionally, scale to a desired set of dimensions. Annotations are adjusted proportionally (except in the case of “fill” below).


### Data Augmentation :

To enhance the diversity and robustness of our dataset, we applied the following augmentation techniques during the training process:

- **Flip:** Horizontal and Vertical
- **Crop:** Minimum Zoom of 0%, Maximum Zoom of 20%
- **Rotation:** Random rotation between -15° and +15°
- **Hue:** Random adjustment between -15° and +15°
- **Exposure:** Random adjustment between -10% and +10%

By utilizing these augmentation techniques, each training example was transformed into multiple variations, exposing the model to a broader range of scenarios. This contributed to improved performance and generalization during the object detection and counting tasks.

### Export your dataset :
Once the dataset version is generated, we have a hosted dataset we can load directly into our notebook for easy training.
One way to download a dataset from Roboflow Universe is to use our pip package. we generate the appropriate code snippet directly in our UI. On a dataset’s Universe home page, click the Download this Dataset button and select YOLOv8 export format.
After a that , we can see a code You can copy and paste it into your Jupyter Notebook or a similar environment. When you execute it, the dataset will be downloaded to your machine in the appropriate format.

<pre>
from roboflow import Roboflow
rf = Roboflow(api_key='YOUR_API_KEY')
project = rf.workspace('WORKSPACE').project('PROJECT')
dataset = project.version(1).download('yolov8') 
</pre></p>

## Training
The YOLOv8 model was trained on the annotated dataset using the Roboflow platform. The training process involved optimizing the model to accurately detect and classify the various denominations of Jordanian coins.The model was trained with the following configuration:

-**Number of Epochs:** 250
**Training Configuration:** Default configurations provided by Roboflow, including data augmentation 
techniques to improve generalization.


## Inference
Once trained, the model can be used to perform inference on new images containing Jordanian coins. Inference can be done either locally using the provided scripts or through Roboflow's inference API. The model outputs bounding boxes around detected coins along with their corresponding class labels and confidence scores.

## Usage

To use the trained model for inference, follow these steps:

1. Clone this repository:
   ```bash
   git clone [https://github.com/your_username/{model_name}.git](https://github.com/AlbaraShehadeh/Jordan-Coin-Detector-YOLOv8-based-Object-Detection-and-Counting.git)
   
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
3. Run inference on an image:
   ```bash


   


## Acknowledgments
This code is based on the YOLOv8l implementation by Ultralytics.See their <a href="https://github.com/ultralytics/ultralytics">GitHub</a> Repository for more information.
