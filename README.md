# FaceSSD

## Q: What is this repository for?
### A: Keeping trained checkpoint results of experimental models of SSD（https://github.com/tensorflow/models/tree/master/research/object_detection）.


## Q: Who may want to read it?
### A: I am not going to bring any new code or new algorithm here. The python project is from google tensorflow object detection and the setup can be found from opened resources. In practice I found currently the major problem for an AI programmer is not mathamatics or programming skills, it is the speed of the computer. For even training a 320x320 mobilenetv1 SSD models to bussiness level need at least 500M steps on GPU, 50M steps ON TPU. The fastest GPU enviroment I can find can only run 4 steps one second, which means training 500M steps will take more than half month. It is a read headache when writing some innovative modes. Here I do some experimental work of training try to find ways of improving the speed of training.


## Q: What the experimental work will be done?
### I try to solve several puzzles in the followling days and recording the result here. 
1. 
