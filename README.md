# PCB Anomaly Detection

This project focuses on PCB images and the anomalies that occur during the process of manufacturing. This is important since PCB's are generally small and delicate to handle. Identifying anomalies within these PCBs using hardware or man-force can cause further damages to them.

Anomalies like Missing Hole, Spurious Copper, Mouse Bite, Open Circuit, Short, Spur, Spurious_Copper are analysed and detected using YOLOv8 and CV2.

## Pre-Processing

Resizing Images to 640x640 to make all the images the same size which will help in computation and speed of training the model.

Converting RBG images to Greyscale and further to Binary images. This is done to, again, reduce computuation power needed and imcrease the speed needed for the model. We are converting RGB into two types of images to compare which one performs the best. Conversion to Greyscale and Binary images were done using Histogram Equalisation.

Examples:

<p align="center">
  <img src="https://github.com/user-attachments/assets/e4b8293d-1eca-4774-83c4-5e5725c5a86a" width="300">
  <br>
  <b>RGB Image</b>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/5d011db8-13b3-46af-8a41-64ef33d25e59" width="300">
  <br>
  <b>Greyscale Image</b>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e8110494-74cb-495d-b187-f60c84e5f29e" width="300">
  <br>
  <b>Binary Image</b>
</p>

## Model Training

1. K-Fold Cross validation was performed on both Greyscale and Binary images.
2. YOLO was used on Greyscale and Binary images.
3. Model was trained on the Greyscale and Binary images.

## Results

When the model goes through the testing dataset, it creates annotations which are saved with the same name as the image. 
I used average confidence as the evaluation metric. Here, confidence means the value that the identified area hasn anomaly. This is calculated by converting the annotations of that image (which is given in the dataset) and the annotations that the model generates for it.

The average confidence for Greyscale Images : **0.6649**
The average confidence for Binary Images : **0.7564**

**From this, we can see that using Binary Images proves to be better and produces more accurate results.**






