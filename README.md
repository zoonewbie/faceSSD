# FaceSSD

## Q: What is this repository for?
### A: Keeping trained checkpoint results of experimental models of SSD（https://github.com/tensorflow/models/tree/master/research/object_detection）.


## Q: Who may want to read it?
### A: I am not going to bring any new code or new algorithm here. The python project is from google tensorflow object detection and the setup can be found from opened resources. 
### In practice I found currently the major problem for an AI programmer is not mathamatics or programming skills, it is the speed of the computer. For even training a 320x320 mobilenetv1 SSD models to bussiness level takes at least 500M steps on GPU/50M steps ON TPU. The fastest GPU enviroment I can find can only run 4 steps one second, which means training 500M steps will take more than half month. 
### It is a real headache when writing some innovative modes. Here I do some experimental work of training to find ways of improving the speed of training.


## Q: What the experimental work will be done?
### I try to solve several puzzles in the followling days and record the results here. 
### 1. Try to train the model without fine tune checkpoints and find out the minimum steps when models begin to build instinct。  
### 2. Try a new way of training SSD: at first set the model at 150x150, then modify to 360x360 and continue training, then 512x512.
### if the above trying fails, I may try to use the previous training checkpoint as fine tune of the further training.


## Update: 
### step 1: mobilenetV1 is the fastest to train. 
![mobilenetV1 150x150 300K](https://github.com/zoonewbie/faceSSD/raw/master/keypoints/v1/v1_150x150_300K/Screenshot3.png) 
![mobilenetV1 150x150 300K](https://github.com/zoonewbie/faceSSD/raw/master/keypoints/v1/v1_150x150_300K/Screenshot5.png) 
 

### step 2: mobilenetV1/TPU/batch size 128/500K.
![mobilenetV1 150x150 500K TPU](https://github.com/zoonewbie/faceSSD/raw/master/SSD/v1/TPU/Screenshot1.png)
![mobilenetV1 150x150 500K TPU](https://github.com/zoonewbie/faceSSD/raw/master/SSD/v1/TPU/Screenshot2.png)
### Evaluation result shows that even though training on TPU yields lower values of loss(batch size 128/500K steps on TPU vs. 300K steps on GPU). GPU's work is better.

