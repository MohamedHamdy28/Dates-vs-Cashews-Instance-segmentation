# Dates-vs-Cashews-Instance-segmentation
Training YOLOv8 and Mask RCNN models to segment cashews and dates

The colab notebook: https://colab.research.google.com/drive/1yH6tugSHDy_Rta7EKo7ddnxr16gNqjZv?usp=sharing


# Assignment description:

1. Take photos of your environment of two or more objects. (at least 100 instances between all objects) 

2. Annotate them on Roboflow for segmentation. 

3. Train a Mask RCNN model using detectron2

4. Train Yolov8  the smallest size for segmentation

5. Evaluate both models based on mAP and speed and size.

# Solution:

The first problem that I faced during solving this assignment was what objects to segment then I decided to choose dates and cashews and there is a story behind it!

## The story:

One day I was watching a movie and I wanted some snacks but I was too lazy to go to the kitchen and get some, so I thought what if there was a robot that can do this for me? life will be much easier. So I decided to bring humanity one step closer to staying in bed while being served by robots and train a model that can detect Dates and Cashews.

## How did I collect the dataset?

I went to the market and bought some dates and cashews then I returned home and took some photos of them in different environments and light conditions.

![IMG_20230302_153718](https://user-images.githubusercontent.com/71794972/222924117-e2fc970a-59cd-4903-a48b-110485d84a6a.jpg)
![IMG_20230303_133244](https://user-images.githubusercontent.com/71794972/222924126-4706e4f9-332b-4a71-95af-894f3376cf2e.jpg)

## How did I annotate the data?

I annotated the data by using a tool called roboflow then I added some preprocessing and augmentations to increase the size of the data:

- Flip: Horizontal
- 90° Rotate: Clockwise, Counter-Clockwise
- Rotation: Between -15° and +15°
- Crop: 0% Minimum zoom, 20% Maximum zoom

# Training a Mask RCNN model:

For training a Mask RCNN model:

- Imported a notebook from the detectron2 GitHub page
- Chose an architecture for the model
- Imported the custom data
- Trained and evaluated the model


![image](https://user-images.githubusercontent.com/71794972/234708552-7e164598-8453-4231-95f0-4ef8edcedb08.png)
![image](https://user-images.githubusercontent.com/71794972/234708713-1c507be6-2216-44bb-bbfc-695b4555fb22.png)
![image](https://user-images.githubusercontent.com/71794972/234708778-a43365cf-0b6c-4e44-b8b5-b35153ff57ad.png)




# Training a YOLOv8 segmentation model:

For training a YOLOv8 model:

- Imported a notebook from roboflow
- Imported the custom data
- Trained and evaluated the model

![image](https://user-images.githubusercontent.com/71794972/234708946-4a52e3b3-6231-4745-9050-279619dc5ccf.png)
![image](https://user-images.githubusercontent.com/71794972/234709000-d0682a4f-22e6-4732-bc48-8575e884c769.png)



# Evaluation of the models

## Mask RCNN:

**mAP** = 78.248

**inference time** = 186.115 ms per image

**Size:**: 242Mb

## YOLOv8:

**mAP** = 98.1

**inference time** = 57.1ms per image

**Size:** 23.3Mb

# Conclusion:

By looking at the mAP, inference time, and size of each model we can conclude that YOLOv8 used for segmentation is much better option than Mask RCNN. YOLOv8 has higher mAP, faster inference time, and smaller size than Mask RCNN.
