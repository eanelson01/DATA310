## 7/19/21 Response Traffic and Iris Dataset

### Describing the Plots of the Models

#### Traffic
![img_2.png](img_2.png)
- This is the model for the traffic dataset. The first couple blocks are the initial inputs, including the temperature, rain, snow, clouds_all, holiday, weather_main, weather_description, and date_time. The first four combined into a concatenation block. This puts the variables together. Below that, the last 4 variables got StringLookup, meaning that their string values were turned into indices with binary values. From here, the concatenation block was moved into a normalization block above. This means that the mean and variances were adjusted for the numerical values. The StringLookup blocks were changed into Category Encoding blocks. Finally, the four remaining blocks were put into a concatenation block as an output. 
#### Iris
![img.png](iris_model_image.png)
- This is the model for the iris dataset. The first 4 boxes represents the inputs into the model. These include the Sepal_length, sepal_width, petal_length, and Petal_width. The next top box represents the Sepal_length and sepal_width in a concatenated form. Below that is the petal_length transformed from a string to an integer indices as a vocabulary by the StringLookup transformation. This is a transformation to make it easier to predict from the input. The same StringLookup transformation was applied in the box below but to the Petal_width this time. The next top layer is normalization, a type of standardization that makes the variances and means equal among the numerical values. Below that is a block of Category Encoding for the transformed petal_length. This changes the indexes into a float32 type. This same transformation was applied to the petal_width in the box below. Finally, there is the Concatenate block which takes all the inputs from the three blocks in front of it together, so it is fed into the model. This shows 3 total paths to the concatenation stage. This is a necessary step so that it can be one tensor to put into the model.

### Outputs from the Model
#### Traffic
- I was able to run the model once I changed the datatype of certain columns in the dataset from strings to floats and integers. The resulting loss was 3524826.5000. This means that the model is extremely poor at predicting the traffic volume. 
- The target for the traffic dataset is the traffic volume. This is a continuous variable that represents how much traffic there is. The output of the model is a prediction of what the traffic_volume is based on the other input features. This model uses a Mean Squared error loss function for the accuracy because it is assessing a continuous variable. This is looking at how far off the prediction is from the true continuous volume. 


#### Iris
- I cannot get a result for the iris dataset because I am getting an error saying ¨Function call stack:
  train_function¨ when I go to fit the model. I will continue to try to fix it but currently can´t figure it out. 
- The target for the iris dataset is the species represented by an integer from 1 to 3. This is as such a classification rather than a regression problem from above. For this reason the loss function of the model is a Sparse Categorical Cross Entropy. This is measuring what the predicted species is based on probabilities from 0 to 1 because of soft max applications. The output is an integer from 1 to N and corresponds to the species. 