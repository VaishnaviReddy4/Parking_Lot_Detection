### Parking Lot Detection using Masked Region Based Convolution Neural Networks.

>* #### **Abstract**
Our project treats the problem of long vehicle congestions and untidy parking as an instance segmentation problem to identify cars from an image of a parking lot and infer empty parking spots in the image, using Res Net classifier. It uses deep learning model Mask R-CNN which is pre-trained on MS-COCO dataset and is used for identification of cars and subsequently, parking spots in the input images. This solution uses Computer Vision and Image Processing to identify available parking spaces from parking lot camera images. The vacant slots in parking lots is then sent as a message to the user using Twilio API.  The problem is to identify available parking spots in the parking areas given bird’s eye view images of the parking lots captured by the cameras using Computer Vision and Image Processing. The 3 main considerations include, to detect cars, to propose the R.O.I(Region Of Interests) and to notify with an SMS. 

>* #### **Methodology**

![image](https://user-images.githubusercontent.com/94667797/170271202-c173fcaf-262e-4cb1-a126-3e35e572349e.png)

Image is run through the CNN to generate the feature maps. Region Proposal Network (RPN) uses a CNN to generate the multiple Region of Interest (ROI) using a lightweight binary classifier. It does this using 9 anchors boxes over the image. The classifier returns object/no-object scores. 
Non-Max suppression is applied to Anchors with high object ness score. The ROI Align network outputs multiple bounding boxes rather than a single definite one and warp them into a fixed dimension. 
Warped features are then fed into fully connected layers to make classification using soft max and boundary box prediction is further refined using the regression model. 
Warped features are also fed into Mask classifier, which consists of two CNN’s to output a binary mask for each ROI. Mask Classifier allows the network to generate masks for every class without competition among classes
It uses deep learning model Mask R-CNN which is pre-trained on MS-COCO dataset and is used for identification of cars and subsequently, parking spots in the input images. 
The first part of the problem is to identify all parking spaces in a parking lot from the camera images. 
The second part works on detecting empty parking spaces from a new image input to the system using locations of parking spaces identified in the previous phase. 



>* #### **Highlights**

This solution treats the problem as an instance segmentation problem to identify cars from an image of a parking lot and infer empty parking spots in the image.
It has an additional branch for predicting segmentation masks on each Region of Interest (ROI) in a pixel-to pixel manner. For a candidate object, it has 3 outputs: A class label, a bounding-box offset and the object mask.
As it doesn’t predict all the objects due to the classifier we are using, it would be very easy for the detection of cars which is not messy.
The bounded boxes are created only for the cars (here by the Res Net classifier).
Mask R-CNN extends Faster R-CNN.

![image](https://user-images.githubusercontent.com/94667797/170271703-cc242e39-be4a-4293-b374-c5387fa8b4a6.png)

>* Calculated Frames to obtain output video without giving bounding boxes.

![image](https://user-images.githubusercontent.com/94667797/170271648-29038823-7525-47d7-8e68-f62f46977e4c.png)

  
>* Calculated Frames to obtain output video with given bounding boxes.

![image](https://user-images.githubusercontent.com/94667797/170271878-89b6a446-24f7-4034-b19a-9eeff14e4896.png)

![image](https://user-images.githubusercontent.com/94667797/170271967-e13f5d82-0e55-4b7a-8425-e21e84ff8a38.png)


This respository consists of Two different segments:
1. "Before Mask RCNN" consists of python files that are used to draw the bounding boxes arount the cars manually (which is not a Mask RCNN Algorithm).
2. "Mask RCNN" consists of python files that are used to detect the empty lots when a video is given as input. 

This was a comparision based learning work where time and memory complexities are analyzed. 
