# PCB Anomaly Detection

This project focuses on PCB images and the anomalies that occur during the process of manufacturing. This is important since PCB's are generally small and delicate to handle. Identifying anomalies within these PCBs using hardware or man-force can cause further damages to them.

Anomalies like Missing Hole, Spurious Copper, Mouse Bite, Open Circuit, Short, Spur, Spurious_Copper are analysed and detected using YOLOv8 and CV2.

## Pre-Processing

Resizing Images to 640x640 to make all the images the same size which will help in computation and speed of training the model.

Converting RBG images to Greyscale and further to Binary images. This is done to, again, reduce computuation power needed and imcrease the speed needed for the model. We are converting RGB into two types of images to compare which one performs the best. Conversion to Greyscale and Binary images were done using Histogram Equalisation.

![image](https://github.com/user-attachments/assets/e4b8293d-1eca-4774-83c4-5e5725c5a86a) 
**RGB Image**




