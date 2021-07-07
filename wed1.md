## 7/7/2021 Response 

1. "From the Preprocess the data section of the script, modify the training image to produce three new images"
   - Response
2. "Under the Make predictions section, present the array of predictions for an image from the test set other than the one given in the example script. What does this array represent?"
   - The array represents the probabilities given by the model that the image is a certain classification. For example, index 0 of the presented array is the probability that the image is the object represented by index 0 of class_names, in this case a "t-shirt/top".
3. "How were the Softmax() and argmax() functions applied?"
   - The softmax() function was applied by typing "tf.keras.layers.Softmax()" as an argument in the prediction_model function. The argmax() function was applied by typing np.argmax(predictions[i]) where i is the index of the image desired in the predictions list. The argmax function
4. "Read this post from DeepAI, What is the Softmax function for a description of the two functions (focus on the softmax formula, calculating softmax and the softmax vs. argmax sections)." 
   - The softmax function makes it so that This made it so that the numbers are values from 0 to 1, similar to a sigmoid function. The argmax function from numpy returns the index of the highest probability, representing the class_name that the model predicts the image is. This allows us to check it against the actual label.
5. "Does the output from np.argmax() match the label from your test_labels dataset?"
    - In the case of the image with index 0, the output does match the label from the test_labels dataset. However, it is possible that the argmax() function will produce outputs which indicate a label that is different from the true label. This would indicate a classification by our model.
6. "Under the Verify predictions section, plot two additional images (other than either of the two given in the example script) and include the graph of their predicted label as well as the image itself."
    - Response
7. "Under the Use the trained model section, again select a new image from the test dataset. Produce the predictions for this newly selected image. Does the predicted value match the test label? "
    - Response
8. "Although you applied the argmax() function in this second instance, you did not use Softmax() a second time. Why is that so (please be specific)?"
    - Response
9. "Evaluate how your model for the MNIST dataset compared with your model of the Fashion_MNIST dataset. Which of the two models is more accurate? Why do you think this is so?"
    - Response
