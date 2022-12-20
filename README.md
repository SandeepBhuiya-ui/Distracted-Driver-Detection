# Distracted Driver Detection

Driving a car is a difficult undertaking that needs your full focus. Any action that diverts the driver's attention from the road constitutes distracted driving. Numerous studies have distinguished between three basic categories of distraction: visual (driver's eyes off the road), manual (driver's hands off the wheel), and cognitive (driver's head off the task of driving).

The use of cell phones while driving is now prohibited by law in several states, along with other distractions. We think computer vision can support government initiatives to reduce crashes brought on by distracted driving. Our algorithm informs drivers when they engage in distracted driving behaviour and automatically detects it. In order to reduce accidents caused by inattentive driving, we see this kind of device being integrated into automobiles.

## Data

We took the StateFarm dataset which contained snapshots from a video captured by a camera mounted in the car. 

The training set has ~22.4 K labeled samples with equal distribution among the classes and 79.7 K unlabeled test samples. There are 10 classes of images:
![img-1](https://user-images.githubusercontent.com/97376097/208588558-1b771dc0-2fa8-4c47-9459-ae3f38cea027.png)


## Assessment Metric

Selecting the appropriate metric to assess a model's success is crucial before moving further with its construction. The first metric that springs to mind is accuracy. The best statistic for categorization issues, however, is not accuracy. Accuracy solely considers whether the predicted label matches the actual label, or if the prediction was made correctly. However, determining the degree of certainty with which we label a driver's behaviour as distracted is crucial for assessing the model's effectiveness. Fortunately, we have a statistic called Log Loss that does precisely that.

## Adaptive Learning

Transfer learning is a technique in which a model created for one job is utilised as the foundation for another. The model weights from pre-trained models created for well-known computer vision benchmark datasets, such the ImageNet image recognition challenge, can be reused. For our dataset's number of classes, the last layer with softmax activation is typically removed. The majority of the time, additional layers are also added to better fit the answer to the given task.Given the significant computational and time resources needed to create neural network models for image classification, it is a well-liked deep learning strategy.

## Technology used :
Python libraries : OpenCV, Tenserflow, Scikit Learn, Pandas,...
Computer vision techniques : CNN, Data Augmentation, Transfer Learning

## Some functions for loading and normalization
The 10 classes to classify are :

c0: safe driving 

c1: texting - right

c2: talking on the phone - right

c3: texting - left

c4: talking on the phone - left

c5: operating the radio

c6: drinking

c7: reaching behind

c8: hair and makeup

c9: talking to passenger

##  EDA

### Number of images by category

![plot-1](https://user-images.githubusercontent.com/97376097/208589413-2900a2b9-1c7e-4b32-9a93-4686c50ced70.png)

it is well distributed

### Number of images by subjects

![plot-2](https://user-images.githubusercontent.com/97376097/208589404-75431fcc-dec9-4d97-939f-1f8b7e01724d.png)

## CNN Model 

Architecture :

3 Convolutionnal layers (with Relu, Maxpooling and dropout)

A flatten layer

2 Dense layers with Relu and Dropouts

1 Dense layer with softmax for the classification




