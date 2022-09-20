# Coconut_tree-detection

Coconut tree Detection system, a deep learning model developed on Yolov5 .It is trained and deployed on NVIDIA Jetson Nano kit

## Custom Object Detection(YOLOV5)

### Setting up Jetson Nano Kit:
 follow the page provided by Nvidia for quick setup:
 
 https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit
 
### Deepstream Installation:
Deepstream 6.0(most stable version we found):

https://docs.nvidia.com/metropolis/deepstream/6.0/dev-guide/text/DS_Quickstart.html

### Upgrading up Python 3.9

https://www.itsupportwale.com/blog/how-to-upgrade-to-python-3-9-0-on-ubuntu-18-04-lts/

### Setting up Yolov5:
https://github.com/ultralytics/yolov5

### Training the model:
Change the yaml file according to the classes of the data we have, and change the location of train and valid

Yaml file can be found at Yolov5/data/coco128.yaml

### Testing the model:

#### Detect.py:
open terminal and enter:

    python3 detect.py --weights best.pt --source 0
                                              0,1,2 -camera
                                              
                                              img.jpg
                                              
                                              video.mp4
                                              
                                              url

### Deepstream:

#### Generating weigths
1.Clone the Deepstrean-Yolo Repository

2.go to Deepstream-Yolo/utils/

3.copy gen_wts_YoloV5.py and paste to Yolov5 repo

4.enter the following command in the terminal for generating weights and cfg file:

        python3 gen_wts_yoloV5.py -w best.pt
5.create a folder for inference

6.Copy  generated weights and config files and paste the in yolov5

7.copy and paste deepstream config files into the folder created

8. Edit the config files accordingly

Run the Deepstream-app using following command:

        sudo deepstream-app -c cocotree_config.txt


## Output:

### Image Inference:
![cdece21f-d134-4d59-95ea-b6e2955fbdcb](https://user-images.githubusercontent.com/96674419/191324044-a20e0791-a778-436d-837a-fb84ddd26ad2.jpg)
![e9bfbea6-0537-4a62-93ee-95d738cf95fd](https://user-images.githubusercontent.com/96674419/191324056-a924525d-a900-472a-8897-2b8f7f193b0f.jpg)


### Video Inference:


### Live Inference(Camera) on Jetson: 


https://user-images.githubusercontent.com/96674419/191322549-7c0db398-dc28-49d9-ae99-85d60935f724.mp4

### Using Deepstream :
> for animal intrusion detection

https://user-images.githubusercontent.com/91280385/191314739-a6f7e113-42d6-4bdd-bf4d-ec546a6ea5ff.mp4

