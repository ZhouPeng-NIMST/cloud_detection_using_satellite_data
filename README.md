# Cloud detection using satellite data

## Table of contents
* [Introduction](#Introduction)
* [Future Research and Development](#Future-Research-and-Development)
* [Technologies](#technologies)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)

## Introduction
This project aims to detect clouds using satellite data. It uses the dataset provided in the paper, [Clouds Classification from Sentinel-2 Imagery with Deep Residual Learning and Semantic Image Segmentation](https://www.mdpi.com/2072-4292/11/2/119), to train a deep learning model. There are a total of 100 samples. Each sample in this dataset consist of 10 cloud bands in a TIFF format and a manually labelled cloud mask. Since this is a small dataset, the model needs to be trained using several augmentations and overlapping images. Initially, the model would use only the RGB bands to train. Later, experiments can be done to test models trained on all the bands. 

## Future Research and Development
Detecting clouds would also be an essential step to classify different types of clouds. By properly classifying clouds we can calculate the solar irradiance on earth’s surface. Solar irradiance values can be used to predict the PV output power. 

Detecting clouds would also be the first step if we need to understand the evolution of clouds. Predicting evolution of clouds would enable accurate nowcasting at PV grids. This would enable in efficient operation of a PV grid saving tons of carbon emissions. Predicting the evolution of clouds may also help in faster nowcasting of weather while saving plenty of computations used for Numerical Weather Prediction(NWP).    

## Technologies
* [PyTorch](https://pytorch.org/)
* [NumPy](https://www.numpy.org/)
* [GDAL](https://gdal.org/)


## Features
List of features ready and TODOs for future development
* Visualize different bands and mask of a sample
* Get info of a raster image

To-do list:
* Train and test different SOTA DL architectures used for semantic segmentation like [DeeplabV3+](https://github.com/jfzhang95/pytorch-deeplab-xception). Also train and test the cloudnet architecture as proposed in this [paper](https://www.mdpi.com/2072-4292/11/2/119).
* Deploy the best model such that a user can upload a satellite data file and the model outputs a cloud mask.

## Status
Project is: _in progress_

It took a significant amount of time to understand the problem of cloud detection and find relevant datasets. This required me to go through a plethora of literature associated with the field of Remote sensing which is completely new to me. 
Due to the novelty and complexity associated with the dataset, data samples also needed to be explored to have a richer understanding of the dataset. This is important as it would enable to find the required preprocessing and transforms. Due to the format of data files, it requires creating a custom dataset class to load the data. Once the dataloader is able to adequately load and transform the data, it wouldn't take long to train the model as predefined architectures would be used.


## Inspiration
The project takes inspiration from the paper, [Clouds Classification from Sentinel-2 Imagery with Deep Residual Learning and Semantic Image Segmentation](https://www.mdpi.com/2072-4292/11/2/119) and would also attempt to reproduce its results. 


