# Human Activity Recogniser (HAR)
HAR is a kaggle competition and I am publishing my 2 solutions to it.
In this competition your goal is to build a Human Activity Recognizer (HAR) based on features captured from mobile phone's accelerometer and gyroscope:

    walking
    walking upstairs
    walking downstairs
    sitting
    standing
    laying
## The evaluation metric is a basic categorisation accuracy. The submission .csv file needs to have the following format:
    id,y
    0,1
    1,6
    2,6
My public leaderboard position is 23/40 and 15/40.

The idea behind the solution was to use the PCA in order to decrease the number of parameters from 561 to 166, while capturing 99% of explained variance.
The model is a neural network of 4 layers, that consists of:

    fully connected layer of input size: 166 and ouput 20
    leaky relu with negative slope of 0.1
    dropout of 0.05

    fully connected layer of input size: 20 and ouput 16
    leaky relu with negative slope of 0.1
    dropout of 0..5

    fully connected layer of input size: 16 and ouput 12
    leaky relu with negative slope of 0.1
    dropout of 0..5

    fully connected layer of input size: 12 and ouput 6

As the optimiser I have selected Adam with the learning rate of 0.006 and of the weight decay of 1e-7.

I have chosen to perform 10 epochs to train this neural network and I have plotted the accuracy, validation and training loss to inspect the model performance at each step and to aviod the overfitting on the test data.

To run the model it is recommeded to run the model on GPU titan T4 in google colab.
