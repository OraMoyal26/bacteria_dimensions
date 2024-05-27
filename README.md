This project focuses on the estimation of bacterial dimensions in SEM images, in order to distinguish between acidic bacteria and control bacteria.
<br>

### First step - Object detection:
model training for prediction- We trained a Faster-R-CNN model. This model  is based on TensorFlow's notebook. It trains the model using the train and validation images (JPG format) and annotation files (JSON format). It also saves the trained model for future use. 
The training process is in the Bacteria_FasterRCNN.ipynb file.
data: 
3 folders of images for train, validation and test + annotation files: https://drive.google.com/drive/folders/1GnZJSlIcUDRSqGbOa4IEB5HY2MVzWf1E?usp=drive_link 
The annotation files were created by RoboFlow website. 
Object detection- We used the trained model to detect the bacterial cells and create an annotation file (CSV) and images with bounding boxes(JPG).
The prediction is in the run_model.ipynb file.
data: 
trained model: https://drive.google.com/file/d/1laLCef4tOtV0yG_GMSbcoSw_gHvRp0yT/view?usp=drive_link
images folder: https://drive.google.com/drive/folders/1MsqS9-FwJmP4mHDnPHbEE3lVPpppmfRP?usp=drive_link 

Comparison-  In order to visualize the quality of the model predictions, we compare the predictions and the ground truth by printing the prediction and the ground truth annotations on the same image.
The comparison is in the comparison_test.ipynb file. 
data: 
images folder with predicted bounding boxes from previous code.
annotation file: https://drive.google.com/file/d/1W3f008n1uGtJUGAtqy-bD-DlW-RESaQt/view?usp=drive_link 
Cropping objects-This code cuts the objects in the images and saves each object in a separate image file.
Cropping the objects is in the cropped_objects.ipynb file.
data:
images of objects: https://drive.google.com/drive/folders/1MsqS9-FwJmP4mHDnPHbEE3lVPpppmfRP?usp=drive_link 
annotation file from the prediction created in run_model.ipynb code.

### Second step - Finding good images to measure:
**Finding images** in which you see whole bacteria, not hidden by others and not in the process of dividing. For this purpose we trained the efficientnetv2 model on good and not good images of bacteria. The training and prediction process is in the bacteria_images_classifier.ipynb file. <br>
The model with the weights: https://drive.google.com/file/d/1VgrVh8eiOxCoAHYhGcpXsQ1Geh270zcB/view?usp=sharing<br>
The data on which we trained the model:
https://drive.google.com/drive/folders/1M3bGLWLfv_7JsTvCFsjljgHqbDhgYvRN?usp=drive_link<br>
Images for prediction:<br>
Acidic bacteria https://drive.google.com/drive/folders/1q_-jcjp343pH_KaoDh3cThHvK2eIE3No?usp=drive_link<br>
Control bacteria
https://drive.google.com/drive/folders/1OjLrF8EiktOu-N-1gESjI0o7XFHMncfb?usp=drive_link<br>


### Third step - computational measurement:
**Computational measurement** of the width of the bacteria in the images, and comparison with manual measurement data from the file manual_measurement_data.csv. The computational measurement was done in the measure_width.ipynb file.<br>
The images measured manually https://drive.google.com/drive/folders/1_LVXtcmqz4dfwplicb5_FAD5wNhOD0hX?usp=sharing<br>
Images for computational measurement:<br>
Acidic bacteria https://drive.google.com/drive/folders/1q_-jcjp343pH_KaoDh3cThHvK2eIE3No?usp=drive_link<br>
Control bacteria
https://drive.google.com/drive/folders/1OjLrF8EiktOu-N-1gESjI0o7XFHMncfb?usp=drive_link<br>
