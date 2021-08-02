## Project 4
### Questions
#### How did you modify the data and python script in order to generate comprehensible text?
- There were some modifications that we needed to do before we could feed the initial script into the model. The first thing we did was deleting the descriptions of the characters that appeared between the dialogue. Additionally, we removed the title page that listed the name of the movie, authors, and dates. Lastly, we moved the description of who is talking at each point to the left so that it matched the formatting of the initial Romeo and Juliet script. These data cleaning techniques prepped the script to then be used further. From here, we went through the steps of processing, vectorizing, and predicting that you can read more about [here](“mod4/thursday4.md).

#### Did your output seem to generate text that was relying more on the entire corpus of your screen play (i.e. more associated with long term memory) or was it also able to incorporate some more immediate sequential associations (i.e. more associated with short term memory)?
- The model seemed to be mostly based on short term memory or immediate sequential associations. Most of the time it was capable of getting actual words even if it had some minor hiccups. At times it seemed like it was trying to add a word but it missed it by a letter or two. There didn’t seem to be any major throughline plot, however. It was able to make sense for about a character or two before switching the subject entirely. This made it so the story itself felt very disjointed, but given the limitations it was still impressive. Additionally, it made it so that there were some characters who were saying things that seemed like it was meant for someone else. For example, at one time Ham is talking about going into space on his spaceship. I would expect that longer term memory would have known that the space style phrases were more correlated with Buzz rather than with Hamm. 
#### Did you make any changes to the model itself?
- We made very minor alterations to the script as it seemed to work well with how it was currently constructed. For reading in the script, we used a different open line since it is a new file separate from the Romeo and Juliet file. We used the line “text = open('toystory_v2.txt', 'rb').read().decode(encoding='utf-8')”. This line opens the text and stores it in the object called text. It is simply reading the contents of the file. The only other alteration we made is in regards to the epoch size. Initially the epochs were 20, but we upped it to 300. This allows the model to run for a longer period of time, increasing it’s familiarity with the correlations in the text. We hoped that a larger epoch time would result in better results, which we believe it did. 

#### Were there any unexpected or surprising phrases or statements that were generated by your RNN?
- There were a lot of surprising phrases and statements generated by the RNN. Like we mentioned above, there were some words that were garbled up. Additionally, the subject was constantly changing throughout the script. One example of an interesting phrase from the script was by the character Mrs. Davis who says “Geer aseat. Let's get out of here. Uh...Buzz?  Was that this was notald care up intt some.” I’m not sure what it’s supposed to mean, specifically the “geer aseat” and “notald”. It makes sense where it fails to say in it by putting it together as “intt”. Another odd phrase or mistake is by the TV announcer saying “Multi-phrase voice simulain up intt besind winch un than.” Here is another example of the generator producing the word “innt.” In addition, it says “un”, “besind”, and “simulain” which are all misspelled words. An example of a weird phrase that has mixed subjects is by Woody where he says “Hey, Buzz!! You're flying!!!That's right. Your toys up thrre and you just tell the nice toys that you're not dead.” This phrase mashes up the scene of Woody flying with Buzz and then from earlier in the movie where Woody was talking to the abandoned toys in Sid’s room. These inconsistencies with the subject are what cause the most confusion with the script as it is. There were plenty of phrases that made total sense, however, even with the subjects. One of these is the opening scene: “WOODY: Okay, save your batteries! HAMM: Eh, very good, Woody. That's using the old noodle. WOODY: This is ludicrous.  WOODY: Oh, no!  Sid!!! Get down!!” This is an understandable and almost effective introduction. This example and the others just show the hit or miss nature of the generated text method. 

### Generated Images for Presentation
![img_4.png](toy_story.png)

![img_4.png](buzz.png)
