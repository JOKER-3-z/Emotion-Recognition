# Facial Recognition and Emotion Recognition Base on Yolov8-  
author: HBen  
Edit Time：2023.01.05
### Structure
```
yolov8_DAN_fer
│   README.md  
│   main.py:Use capture of the computer get the image . then show the detection image 
│   Addstudent_name.py: trans the face to feature ,then store to datasets. 
|   config.json: project define
|   face_dataset.json: face datasets
│
└───model
│   │   dan.py: single face FER model
│   │   YOLOV8.py: face Detection
│   │   Arcface.py: face recognition
│      
└───weights
│   │   epochs_18_87.451_DAN.pth : oringional weights
│   │   rafdb_epoch21_acc0.897_bacc0.8275.pth: post train on RafDB dataset ACC:89.7%
│   │   resnet18_msceleb.pth
│   │   yolov8n-face.onnx
│   │   Arcface_rs50.pth
│   
└───util
│   │   facial_pro.py : store some function that process image(alignment、enhancement)
│   │   matlab_cp2form.py:store some function that calculate the similarity
│     
└───ADD_IMAGE
│   │   1.jpg
│   │   ……
└───

```
### How to use
- environments:  
  - python >= 3.7  
  - opencv-python >=4.7.0.72  
  - pytorch >= 1.12.0
  
### Download weight
  Arcface_rs50.pth（链接：https://pan.baidu.com/s/1dna2U7CwUg2Jq6-b_JV4aw?pwd=s2f1 提取码：s2f1）  
  yolov8n-face.onnx （链接：https://pan.baidu.com/s/1jCPZcQhFIZZzj1UOOrLOdw?pwd=s2f1 提取码：s2f1）  
  DAN:{  
    original_weights(ACC:87.45): (链接: https://pan.baidu.com/s/1u1coZFQodq4CFbftvli2vQ?pwd=s2f1 提取码: s2f1)  
    Training base on rafdb（ACC:89.7): (链接: https://pan.baidu.com/s/1T_0IovncTIAHv-tPXEfVBQ?pwd=s2f1 提取码: s2f1
  }
### Run
  - Add face image to ADD_IMAGE floder and set the face_id as the image name eg: 1.jpg（the guy who in the image id is 1）  
  - Automatically convert the face image under the ADD_IMAGE to save the face-dataset.json file as facial features
    ```
    python Add_face_info.py
    ```  
- Then start use
  ```
    python main.py
  ```
      