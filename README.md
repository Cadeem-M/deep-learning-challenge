# Alphabet Soup Applicant Funding Model

## Overview 
The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With my knowledge of machine learning and neural networks, I’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Results

* Data processing:

<p align="center">
<img src="Images\Dataframe.png" width="500px">
</p>

1) The "is_successful" column is the target as the goal of this model is to predict successful applicants.
2) "EIN" and "NAME" columns are dropped from the features data frame as they are identification columns and do not provide pattern data.
3) Thus the remaining columns: Application_type, Affiliation, Classification, Use_case, Organization, Status, Income_AMT, Special_Consideration, and Ask_AMT, are this model's features.

* Compiling, Training, and Evaluating the Model:

<p align="center">
<img src="Images\nodes.png" width="500px">
</p>

<p align="center">
<img src="Images\accuracy1.png" width="500px">
</p>

1) This model uses 4 layers (3 hidden, 1 outter).
    Layer 1 -> 43 neurons (set to be equal to the number of features as a baseline)
    Layer 2 -> 22 neurons (half of layer 1 as we try to approach 1 neuron for our final layer)
    Layer 3 -> 11
    Layer 4 -> 1

2) This model uses relu as the activation function within the hidden layers and it uses sigmoid as the function for the outter layer as it attempts to solve the yes/no question of providing an applicant a loan.

3) This model was able to achieve 72.9% accuracy.

* Attempting to Improve the Model

1) Unique minority values within the Application_type, and Classification columns were further rolled together into a 'other' value to reduce outlier data.
Application_type:
<p align="center">
<img src="Images\app_type1.png" width="400px">
</p>

<p align="center">
<img src="Images\app_type2.png" width="400px">
</p>


Classification:
<p align="center">
<img src="Images\class1.png" width="400px">
</p>

<p align="center">
<img src="Images\class2.png" width="400px">
</p>

2) The number of starting neurons were increased from 43 to 120 and an additional layer was added to help the model capture more patterns in the data. 

<p align="center">
<img src="Images\improved_model1.png" width="400px">
</p>

<p align="center">
<img src="Images\improved_model2.png" width="400px">
</p>

3) Epochs were increased from 75 to 200 to allow for more learning time

<p align="center">
<img src="Images\epoch1.png" width="400px">
</p>

<p align="center">
<img src="Images\epoch2.png" width="400px">
</p>

4) The accuracy of the new model is about 72.4%

<p align="center">
<img src="Images\accuracy2.png" width="400px">
</p>



## Summary
We were not able to achieve our goal of a model with 75% accuracy. Our initial model managed to achieve an accouracy of 72.9% which is just decent with room for improvement. To improve the model, the Application_type, and Classification columns from the data were adjusted to combine "rare occurances" in the data into one category so that they individually had less impact on model. Additionally, we increased the number of neurons, layers, and epochs in the second model to help capture more patters in the data and allow for more learning cycles this did not help. Instead, we saw a small decrease in accuracy from 72.9% to 72.4%. 
