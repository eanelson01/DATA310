## 7/29/2021 Response

### Methods

#### Processing, vectoring, and predicting text

- The first thing we did in the script is loading in the Romeo and Juliet script from the link. We did this using the get_file function from tensorflow and keras. We then read the text, importing it in the namespace under the object "text". After importing it in, we looked at the number of unique characters in the text using the set function, finding out there was a total of 65 unique characters. To process the text, we converted the strings into numeric representations using the preprocessing.StringLookup function. This allowed us to then transfer the tokens into character ID's as numeric values. Once we wanted to get the actual letters rather than the numeric representation, we used the same preprocessing.StringLookup function but with the argument "inverse" set to True. We were able to then rejoin these values by using the tf.strings.reduce_join function. From here, we created training examples and targets to eventually give to the model. To do so, we first used teh from_tensor_slices function to cut the string into a series of character indices. Then we used the batch method in order to go from the characters to entire sequences. Lastly, we made batches with a size of 64 each. 

#### Building and training the model

- The model we used has an embedding layer with a total of 16896 parameters. Next was a gru layer that had a total of 3938304 parameters. Lastly, there was a tense layer which had a total of 67650. Altogether there were 4,022,850 parameters in the entire model. We used SparseCategoricalCrossentropy as the loss function because this is much more than just binary outputs. There are multiple classes. The output has a shape of (64,100,66) which represent the batch size, sequence length, and vocab size respectively. We compiled the model using an adam optimizer. After building the model, we fit the model to the dataset for a total of 20 epochs. 

#### Generating Text

- We generated the text using the model we trained. We ran a loop where it predicted the next letter for each loop. This prediction was based on the letters that came previously from it. This was made using the trends that the model found in the dataset and the larger epoch size allowed for the model to understand these trends more in depth. This process then produced the text below which is based on the Romeo and Juliet play. 

### Generated Text:

"ROMEO: Go to keep I heard that please these solding. 

DUKE VINCENTIO:
I tell thee, Lady: set down--
As Triming admory? let me know them in the rest,
Can come the market-place; which he says he
Were founds it, 'tis true.

VILGILIA:
My has counsel
Tell me to the seat. Come, Camillo,
Not when I have not in men found
By love I am being dishralf with you along
With in a pity two marchion, or aduet
Is steples to his timorous saint.

CLAUDIO:
Fear thou the general witch shade thy too, and not as had
As little have been lends, ere I should live,
Sediding his smadless sand to to the Volscian's,
It is aparletol's place: it hath slept I make it
and received.

LEONTES:
She is fault: making a woman worship and deceared: shall turn
To try if the deputed friends on our revenge
First he will answer into his mistress,
Vincention, most overtague.

LEONTES:
Come, let me aship; thy sweet for my good lord,
But that our birds is but to resist weapon.

ISABELLA:
The worst is death.

Boans, And not deliver'd Horten "

#### Analysis of the generations:
- The text seems to be mostly understandable, at least in the context of Shakespeare which is barely understandable to begin. There are some words that it produced which appear to not actually be words. It's a jumbled sort of letters. This is somewhat expected considering it is character by character instead of word by word. Additionally, we only ran the model for 20 epochs so it would be advantageous to run it for additional time to see if the results are better. Overall, it's impressive to see that machine learning methods can find trends in English and then produce its own scripts.