## Preparing Dataset

For segmetation network , you can download the corresponding dataset as the [this link](http://www.cvlibs.net/download.php?file=data_road.zip). Then you can set it as the root of the segmentation model root directory as showed below :

```

Deep_Learning_Final_Project
├── segmentation-model
│   ├── __init__.py
│   ├── data-road
│   ├── dataset.py
│   ├── fcn.py
│   ├── train.py
│   ├── utils.py
│   ├── vgg.py
│
│── Video-streaming

```

![](https://i.imgur.com/ZVHlomh.png)

## Model training 

You can train the model by the following command


```
python3 train.py --output_dir "inference/" --root_dir "data_road"
```

## Video Streamming : 

Use the terminal under the Video-streaming directory

```
Deep_Learning_Final_Project
├── segmentation-model
│── Video-streaming
    ├--deploy-alaxnet.prototxt
    ├--requirement.txt
    ├--streaming.py
    ├--alexnet.caffemodel
```

![](https://i.imgur.com/nML5K8A.png)

You should elavalate webcam priority in ubuntu first by  : 

```
sudo chmod 777 /dev/video*
```

And you can check whether your webcam can work by install the following application
```
sudo apt-get install guvcview
sudo apt-get install cheese
```

Set up the  required package

```
pip3 install -r requirement.txt
```

now you can start real time material recognition by the following command :

```
python3 streaming.py -p deploy-alexnet.prototxt -m alexnet.caffemodel
```