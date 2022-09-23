# Birdclef 2022
Master Project Work

This project ist based on the 2022 Kaggle BirdCLEF challenge: \
https://www.kaggle.com/competitions/birdclef-2022

We didn't get our model ready in time to actually submit to the competition. This project was mainly done for exercise purposes and playing around with different models and model configurations. Instead of going for the most state-of-the-art-approach right away we spent a considerable amount of time on a more simple approach that did a lot more things manually than the more advanced pretrained models do these days.

## Project structure
### EDA
We were three people working on this project and in the EDA phase every one of us followed their own approach to exploring the data.\
The three notebooks do contain duplicate code since they were created independently from each other.

### Data
*This does not contain the actual training data.* \
It just contains files that were generated for the training process, namely a simple list of all the training data with their encoded class label.

### images
During our EDA and the data preprocessing we had generated some images and wanted to save them in a dedicated place. \
Most graphs however were *not* explicitly saved and can be found inside the notebooks outputs.

### models
Pretty straight forward, two different models were used. \
The subfolder structure of the efficientNet was created by the lightining flash framework. The *logs* folders contain all the data for the different training configurations, checkpoints and performance metric graphs. \
All the different model configurations were saved after training the network, the resulting models can be found in the *saved-models* folder.

### preprocessing
During development of our preprocessing chain different approaches were explored. Some of those are to be found in the testing folder. \
The regular *spectrograms* notebook was used to generate the folder structure and the simple, non processed versions of the spectrograms. \
Later on after having successfully trained some models on the basic data we went back and built a more sophisticated chain of processing steps for the spectrograms (to be found in the *normalized_spectrograms* notebook)

### results
This folder *only* contains performance metrics for the simple CNN since the framework for the efficientNet brought along it's own folder structure to save those data. The *model-comparison* notebook plots the performance graphs for all the efficientNet training configurations to have them all in one place for comparison.

## How to get it running on your own system
*This Project was run on a local Computer, take all the following instructions to get it running on your own machine with a grain of salt. Reproduceability wasn't the highest priority...* \
Training was done on a system with an Intel i7 6700 and a GTX 1070 and took anything from 10 minutes to 8 hours depending on the configuration.

1. Download the data from the Kaggle challenge
2. run the *spectrograms.ipynb* notebook:
    * Some adjustments to the Constants at the top might need to be made depending on the folder structure at hand
    * Run *add_folder_structure* first and then *generate_spectrograms*
    * This will generate a lot of data (roughly 20 Gig of data for our chosen format of spectrograms)
3. If the simple spectrograms are to be used (spoiler, they are better than the processed ones) one can just run one of the model configurations to start training after having generated the spectrograms (either *LeNet.ipynb* or *Lightning-efficientB0.ipynb*)
 
