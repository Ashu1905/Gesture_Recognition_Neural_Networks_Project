# Gesture_Recognition_Neural_Networks_Project

Developed by:
[Ashwini Abhang](https://github.com/Ashu1905)


### Problem Statement
Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:
 
| Gesture | Corresponding Action |
| --- | --- | 
| Thumbs Up | Increase the volume. |
| Thumbs Down | Decrease the volume. |
| Left Swipe | 'Jump' backwards 10 seconds. |
| Right Swipe | 'Jump' forward 10 seconds. |
| Stop | Pause the movie. |

Each video is a sequence of 30 frames (or images).

### Understanding the Dataset


The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use.

Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Hence, you will need to do some pre-processing to standardise the videos.

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

Your task is to train a model on the 'train' folder which performs well on the 'val' folder as well.

### Objectives:
1. **Generator**:  The generator should be able to take a batch of videos as input without any error. Steps like cropping, resizing and normalization should be performed successfully.

2. **Model**: Develop a model that is able to train without any errors which will be judged on the total number of parameters (as the inference(prediction) time should be less) and the accuracy achieved. As suggested by Snehansu, start training on a small amount of data and then proceed further.

3. **Write up**: This should contain the detailed procedure followed in choosing the final model. The write up should start with the reason for choosing the base model, then highlight the reasons and metrics taken into consideration to modify and experiment to arrive at the final model.



### Results:
![Results table](https://user-images.githubusercontent.com/69676151/189583880-039eade6-bd97-4e78-ad76-d02da5dab2ad.jpg)

### Best Models:
<br>

1. **Conv3D** - The best results for this approach was obseved in *Conv 3D Model with 20 frames per video
16, 32, 64, 128 filters conv 3D layers + 256ense layer + 128 dense layer + image size 120 by 120* which had the metrics as follows:- 
    - Training Accuracy: 93.67 %
    - Validation Accuracy: 88.00 

<br>


2. **Conv2D + RNN** - The best results for this approach was observed in *Mobilenet (re train all weights) + 64 dense nodes* which had the metrics as follows:-
    - Training Accuracy: 99.85 %
    - Validation Accuracy: 97.00 %

<br>

### Conclusion:- 
Hence I was sucesssfully able to design a gesture recognition model using two different approaches viz. Conv3D approach and Conv2D+RNN approach. <br>
For Conv2D I used transfer learning with mobilenet model. <br>
Both the approaches performed very well with training accuracy of `93.67 %` and `99.85 %` respectively. <br>
It also performed well on the `validation data` with accuracy of `88.00 %` and `97.00 %`
