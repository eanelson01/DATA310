## Thursday Response 7/15 

1. Using the relevant parts from the entirety of the example script as a guide, fit a CNN model to your training data and validate using the beans dataset from Tensorflow datasets and then again train and validate using the eurosat dataset. Present your results and discuss the accuracy of each of model.
    - After running both datasets through the model I came across the following results and accuracies. The results were of some surprise to me.  I was expecting the bean model to do better than the EuroSAT dataset beacuse I was expecting the beans to be a less complex dataset. This is because it has 3 classes compared to 10 with the EuroSAT. I tried fitting with the val_ds and test_ds as the validaiton set and posted the results. The test did better because it was building off the results of the val_ds is my guess.
      
        | Beans or EuroSAT | Validation | Test|
        | --- | ----------- |-------|
        | Beans | 0.6796 |.8041|
        | EuroSAT |  0.7584   | .8249 |
       
      
2.  "Apply this same method to both the beans and eurosat datasets. Did your model performance improve? How many epochs were you able to run and how much time did it take? Present your results and discuss the accuracy of your augmented output for tomorrow's class."
    - Adding the augmentation resulted in the following results and accuracies. It was a drastic decrease in accuracy and made it so that the model took longer to train. I did 3 epochs for each because I saw that the model was not accurate or gaining overall accuracy. Each training took around 5 minutes for the bean dataset and 3 minutes for the EuroSAT dataset. This round followed my inclination more that the beans model would be better than the  
      
        | Beans or EuroSAT | Validation | Test|
      | --- | ----------- |-------|
      | Beans | .2987 |.3507 |
      | EuroSAT |  .2436  | .3123 |
