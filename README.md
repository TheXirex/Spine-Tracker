# Spine-Tracker
## Context
People who work at a computer have back problems due to prolonged sitting and incorrect workstation ergonomics. Repetitive arm movements and a posture in which the neck and back are inadequately supported can lead to a variety of medical problems, including back, neck and shoulder pain, as well as possible spinal disorders.

**Main goal:** develop an algorithm for human back position tracking.

## Selected Сlasses
Selected activity classes for the spine:
- straight spine
- curved spine
- leaning spine
- tilting to an object lying on the floor from 3 positions
- reaching for an object from a shelf from 3 positions

![classes](https://github.com/TheXirex/Spine-Tracker/assets/104722568/2b1967c0-fe04-451d-b16e-622afd98b159)

## Prototype for Data Collection
Collection was performed using two phone devices.

![prototype](https://github.com/TheXirex/Spine-Tracker/assets/104722568/e16cae12-db3c-48f0-ba0c-17f5f3a00541)

## Preprocessing
To review all aspects of data processing and preparation; model training and testing - you can view the .ipynb files provided in the repository.

## Results
- Using the prototype created and two phones, a data set of 45000 instances was collected, with a data fetch rate of ~50 Hz (equivalent to 15 minutes of recording).
- After a series of transformations, a set of data for training the neural network would be obtained.
- Taking the statistical parameters of the accelerometer and gyroscope axes as features, we obtained a dimensionality of 144 columns. 
- After applying analysis and feature importance algorithms, out of 12 starting parameters, 5 became features, and the dimensionality decreased to 60.
- Since the data was collected from only one person, the accuracy of the model reaches 99.87% (for a larger sample, it is worth reconsidering the number of input parameters).
- The data collected by me can not be considered perfect, as there is minimal asynchrony (due to the impossibility of simultaneous start of recording from two different devices not designed for recording).
- Finally, after a series of tests, the algorithm of processing 1 data packet (120 measurements in a particular case) takes 0.17 seconds and 0.8 Mb of memory on average.

## Requirements
1. numpy==1.26.1
2. pandas==2.1.1
3. scikit-learn==1.3.2
4. matplotlib==3.8.0
5. seaborn==0.13.0
6. scipy==1.11.3
7. tensorflow==2.14.0
8. joblib==1.3.2
9. psutil==5.9.0
10. tabulate==0.9.0
