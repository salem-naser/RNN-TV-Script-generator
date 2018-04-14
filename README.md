# RNN-TV-Script-generator
Recurrent neural network implemented using Tensorflow

In this project, I have generated my own Simpsons TV scripts using recurrent neural networks (RNNs). 
The Jupyter notebook [dlnd_tv_script_generation.ipynb](https://github.com/TeaP/RNN-TV-Script-generator/blob/master/dlnd_tv_script_generation.ipynb) contains my solution to the third of in total five project given as a requirement for the 
[Udacity Deep learning Nanodegree](https://www.udacity.com/course/deep-learning-nanodegree--nd101). 

I've used part of the Simpsons dataset [Simpsons dataset](https://www.kaggle.com/wcukierski/the-simpsons-by-the-data) of scripts from 27 seasons. The neural network generates a new TV script for a scene at Moe's Tavern.

The data sets used in the training are contained in the file [moes_tavern_lines.txt](https://github.com/TeaP/RNN-TV-Script-generator/blob/master/moes_tavern_lines.txt). A sample data set would be the text of a scene with one of Bart's prank calls to Moe:

```
Moe_Szyslak: (INTO PHONE) Moe's Tavern. Where the elite meet to drink.
Bart_Simpson: Eh, yeah, hello, is Mike there? Last name, Rotch.
Moe_Szyslak: (INTO PHONE) Hold on, I'll check. (TO BARFLIES) Mike Rotch. Mike Rotch. 
Hey, has anybody seen Mike Rotch, lately?
Moe_Szyslak: (INTO PHONE) Listen you little puke. One of these days I'm gonna catch you, 
and I'm gonna carve my name on your back with an ice pick.
Moe_Szyslak: What's the matter Homer? You're not your normal effervescent self.
Homer_Simpson: I got my problems, Moe. Give me another one.
Moe_Szyslak: Homer, hey, you should not drink to forget your problems.
Barney_Gumble: Yeah, you should only drink to enhance your social skills.
```
<a href="http://www.youtube.com/watch?feature=player_embedded&v=lj6LnihWpOg" target="_blank"><img src="http://img.youtube.com/vi/lj6LnihWpOg/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

<img src="https://vignette.wikia.nocookie.net/simpsonstappedout/images/1/10/Moes_bar_s.jpg/revision/latest?cb=20140303081347" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>


<img src="https://www.spicenews.com.au/wp-content/uploads/2014/05/moes.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>



The solution was made using the [Test-driven development (TDD) software development process](https://www.madetech.com/blog/9-benefits-of-test-driven-development) and the unit tests provided in [problem_unittests.py](https://github.com/TeaP/RNN-TV-Script-generator/blob/master/problem_unittests.py). 

The environment should be created using [requirements.txt](https://github.com/TeaP/RNN-TV-Script-generator/blob/master/requirements.txt).

# Solution

The solution includes the following: 
1.  Function for creating lookup tables: dictionaries that map a word from the vocabulary to a unique integer and vice versa, an integer to a word from the vocabulary. 
2. Function for the token lookup, in order to replace punctuation with tokens (e.g.  ',' is replaced by '||Comma||'). 
3. Creating placeholders for the inputs, targets and learning rate. 
4. Building the RNN cells using ***tf.nn.rnn_cell.BasicLSTMCell*** and ***tf.nn.rnn_cell.MultiRNNCell***. 
5. Word embedding. 
6. Building the RNN using ***tf.nn.dynamic_rnn***. 
7. Applying the above functions. 
8. Creating batches. 
9. Neural network training including setting hyperparameters:
+ ***num_epochs*** to the number of epochs,
+ ***batch_size*** to the batch size,
+ ***rnn_size*** to the size of the RNNs,
+ ***embed_dim*** to the size of the embedding,
+ ***seq_length*** to the length of sequence,
+ ***learning_rate*** to the learning rate.
10. Picking the next word using ***np.random.choice***.

The TV Script is nonsensical (doesn't make any sense), since the training was on than a megabyte of text. 

```
moe_szyslak:... i didn't rip out his voice box, but i did stretch out.
chief_wiggum: uh, hello? we can get back in business... uh, i was gonna go homer in the stuff here.
marge_simpson: what?
homer_simpson:(grunt) what's the hubub book, boys.
moe_szyslak: yeah, i know, your dad's the two thing to do. and now, i know, this is notably thing.
carl_carlson:(worried) i'm the best of this than moe's. it, uh, good uh, let me check. but, 
i'm gonna do something with my partner, made in the air room. he might have better to buy him.
moe_szyslak: listen to dumb? oh, i ain't be mad at those all life.
lenny_leonard: what are you going?
homer_simpson: marge_simpson: when you're right, moe. don't as nothin'.
marge_simpson: to put. the answer.
marge_simpson:(sad) yeah, we all got any letter before...(smug laugh)
```
    


 




