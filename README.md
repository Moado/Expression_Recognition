# Expression_Recognition

Expression_Recognition is project for tracking faces and multiple models detection from faces such as:
1.  Gender : _Male, Female_
2.  Expressions : _Anger, Happiness, Sadness, Surprise, Fear, Disgust_
3.  Illumination : _Bad, Medium, High_
4.  Pose : _Frontal, Left, Right, Up, Down_
5.  Occlusion : _Glasses, Beard, Ornaments, Hair, Hand, None, Others_
6.  Age : _Child, Young, Middle and Old_
7.  Makeup : _Partial makeup, Over-makeup_


****Requirements****
 - [Python](https://www.python.org/) 3.*
 - [Imutils](https://pypi.org/project/imutils/)
 - [Numpy](http://www.numpy.org/)
 - [OpenCV](https://opencv.org/)
 - [Pytorch](https://pytorch.org/)

## Run
to use Expression_Recognition execute `run.py` file with  various options
```
usage: run.py [-h] [--cuda CUDA] [--show SHOW] [--delay DELAY]
                  [--inputs_path INPUTS_PATH] [--outputs_path OUTPUTS_PATH]
                  [--models_path MODELS_PATH] [--models MODELS [MODELS ...]]

optional arguments:
  -h, --help            show this help message and exit
  --cuda                set this parameter to True value if you want to use
                        cuda gpu, default is False
  --show                set this parameter to True value if you want display
                        images/videos while processing, default is False
  --tracking            set this parameter to True value if you want tracking
                        faces in images/videos, default is False
  --delay DELAY         amount of seconds to wait to switch between images
                        while show the precess
  --inputs_path INPUTS_PATH
                        path for directory contains images/videos to process,
                        if you don't use it webcam will open to start the
                        record
  --outputs_path OUTPUTS_PATH
                        path for directory to add the precesses images/videos
                        on it, if you don't use it output directory will
                        created and add the precesses images/videos on it
  --models_path MODELS_PATH
                        path for directory contains pytorch model
  --models MODELS [MODELS ...]
                        first index refers to gender model, second index
                        refers to expression model, and third index refers to
                        multiple models
```
   

## Datasets
* [IMDB](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/) ~ 500K image
* [WIKI](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/) ~ 60K image
* [FER](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data) ~ 35K image
* [IMFDB](http://cvit.iiit.ac.in/projects/IMFDB/) ~ 3K image
* [JAFFE](http://www.kasrl.org/jaffe.html) ~ 250 image


## Models
models in this project are based on [Real-time Convolutional Neural Networks for Emotion and Gender Classification](https://arxiv.org/pdf/1710.07557.pdf) paper
model architecture: 


project consist of 3 models:
	

 1. Gender
 2. Expression
 3. Multiple

### Gender Model
trained done by using [IMDB](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/) , [WIKI](https://data.vision.ee.ethz.ch/cvl/rrothe/imdb-wiki/),  [IMFDB](http://cvit.iiit.ac.in/projects/IMFDB/)  datasets. consist of ~ 600 K image, and by using tencrop data augmentation dataset increased to be ~ 6 M image 
Accuracy ~ 78% using only 6 epochs and it will reach higher accuracy expected to be ~ 96 %

### Expression Model
trained done by using [FER](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data) , [IMFDB](http://cvit.iiit.ac.in/projects/IMFDB/), [JAFFE](http://www.kasrl.org/jaffe.html)  image datasets. consist of ~ 40 K image, and by using tencrop data augmentation dataset increased to be ~ 400 K image 
Accuracy ~ 60% using 15 epochs and it will reach higher accuracy expected to be ~ 66 %

### Multiple Models
this model is little bit different form Gender & Expression models 
in this model we use one feature extractor model and 5 different classifiers each classifier predict specific features form faces and they are:
* Illumination : _Bad, Medium, High_
*  Pose : _Frontal, Left, Right, Up, Down_
*  Occlusion : _Glasses, Beard, Ornaments, Hair, Hand, None, Others_
*  Age : _Child, Young, Middle and Old_
*  Makeup : _Partial makeup, Over-makeup_

trained done by using [IMFDB](http://cvit.iiit.ac.in/projects/IMFDB/) image datasets consist of ~ 3 K image, and by using tencrop data augmentation dataset increased to be ~ 30 K image 
Accuracy ~ 77% using 15 epochs

[Real-time Convolutional Neural Networks for Emotion and Gender Classification](https://arxiv.org/pdf/1710.07557.pdf) paper

[Simple object tracking with OpenCV by  pyimagesearch](https://www.pyimagesearch.com/2018/07/23/simple-object-tracking-with-opencv/)

