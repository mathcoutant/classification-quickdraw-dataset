# classification-quickdraw-dataset

## Introduction
The project is about creating a model that can classify the drawings of the [Quick, Draw! Dataset](https://quickdraw.withgoogle.com/data). The Quick, Draw! Dataset is a collection of 50 million drawings across 345 categories, contributed by players of the game [Quick, Draw!](https://quickdraw.withgoogle.com/) by Google. The task is to build a classifier that can recognize the category of the drawing.

## Data
The data used in the project is .ndjson files from the Quick, Draw! Dataset. They can be downloaded [here](https://console.cloud.google.com/storage/browser/quickdraw_dataset/full/simplified;tab=objects?prefix=&forceOnObjectsSortingFiltering=false). These files must be placed in a "data" folder in the root directory of the project. Specify in "class_names.txt" the classes you want to use. Then when calling the preprocessing function, the data will be converted to images and split into training and test datasets.

## Model
The model is a simple CNN model with 3 convolutional layers and 2 fully connected layers. 

I will maybe try different options for the model, like using Transfer Learning with a pre-trained model (VGG or ResNet).

## Results


## Conclusion
The model is able to classify the drawings with an accuracy of 70% on the test data. 
The low accuracy can be explained by sevral factors : 
- The model is very simple.
- The data quality is very heterogeneous. The label can be irecognizable for a human on some drawings.
- When asked to draw a specific object, the players can draw it in different ways. For example, a cat can be drawn in many different ways, and the model has to be able to recognize all of them.
- They also have a very short time to draw the object, so the drawings are often very simple and unclean. This can explained the confusion between flowers and windmill, for example.

The model can be further improved by using more complex models and by using more data.

## References
1. Quick, Draw! Dataset:
https://console.cloud.google.com/storage/browser/quickdraw_dataset/full/simplified;tab=objects?prefix=&forceOnObjectsSortingFiltering=false
2. PyTorch documentation:
https://pytorch.org/docs/stable/index.html