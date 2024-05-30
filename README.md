## Pneumonia or Normal prediction from Chest X-RAY 

**To Clone Repo**
```
git clone https://github.com/shoryasethia/XRay-Penumonia
cd XRay-Penumonia
```
**Dataset**
- Download directly from [here](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

- Run following if using colab
```
!pip install kaggle
!mkdir ~/.kaggle
!mv kaggle.json ~/.kaggle/
!kaggle datasets download -d paultimothymooney/chest-xray-pneumonia
!unzip chest-xray-pneumonia.zip
```
### Results
**Model Architecture**
```
Model: "sequential_10"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d (Conv2D)          (None, 222, 222, 32)      896       
                                                                 
 max_pooling2d (MaxPooli  (None, 111, 111, 32)      0         
 ng2D)                                                           
                                                                 
 conv2d_1 (Conv2D)          (None, 109, 109, 64)      18496     
                                                                 
 max_pooling2d_2 (MaxPooli  (None, 54, 54, 64)        0         
 ng2D)                                                           
                                                                 
 conv2d_3 (Conv2D)          (None, 52, 52, 128)       73856     
                                                                 
 max_pooling2d_4 (MaxPooli  (None, 26, 26, 128)       0         
 ng2D)                                                           
                                                                 
 conv2d_5 (Conv2D)          (None, 24, 24, 256)       295168    
                                                                 
 max_pooling2d_6 (MaxPooli  (None, 12, 12, 256)       0         
 ng2D)                                                           
                                                                 
 flatten (Flatten)        (None, 36864)             0         
                                                                 
 dropout (Dropout)         (None, 36864)             0         
                                                                 
 dense (Dense)            (None, 512)               18874880  
                                                                 
 dense_1 (Dense)            (None, 512)               262656    
                                                                 
 dropout_1 (Dropout)         (None, 512)               0         
                                                                 
 dense_2 (Dense)            (None, 1)                 513       
                                                                 
=================================================================
Total params: 19526465 (74.49 MB)
Trainable params: 19526465 (74.49 MB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________
```

- **NOTE : Total parameters are 19.5+ million**
- **But the training time taken to acheive 99% training accuracy is `658.3010199069977 seconds`**

**Model Accuracy is also descent enough for medical tasks**
![Accuracy](https://github.com/shoryasethia/XRay-Penumonia/blob/main/TestValAccuracy.jpg)

**Some Predictions**
> **0 :** NORMAL  ,   **1 :** PNEUMONIA

![Predictions](https://github.com/shoryasethia/XRay-Penumonia/blob/main/FewPredictions.png)

**If you liked this repo, do give a like**
**Author : [@shoryasethia](https://github.com/shoryasethia)**
