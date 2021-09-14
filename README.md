# 100daysofNLP
From last month i was involve in few personal things and didn't get much time to explore NLP. I wanna be on trek. I want to learn and explore things in NLP consistently. 

So i am taking challenge to learn NLP for 100days to get back to the awesome world of NLP.

During this 100days the goal is to,
* Learn NLP stuff, 
* Contribute to opensource, 
* Read Research paper,  
* Write blog in NLP,
* Build Something New and Opensource it.

The most important thing share it on twitter and Linkedin. Maintain it on this github repository.

## Day1:

Started Learning about Model Interpretability in Pytorch Model using [Captum](https://github.com/pytorch/captum). In NLP we build models with great performance but It's important to know how the model is predicting. What kind of text is focused and observed by neuron/layer/model. 

## Day2:

Worked on Captum, Had word important analysis on my Distilbert trained on Emotion Classification dataset. Below image shows that how words are given importance in with respect to target in the distilbert model. I used Integrated Gradient method for model interpretability for Embedding layers.

![image](images/WordImportance.png)

[Colab Notebook](notebooks/Distilbert_Model_Interpretability_With_Captum.ipynb)

## Day3:

### How to read Researchpaper effectively
I have been reading papers a lot but it was top down approach to go through entire research paper. It wasn't effective appraoch.
Come across this recent [article and video](https://saiamrit.github.io/technical-blog/research/reading_papers/2021/07/31/read-papers.html) Its showing systematic way. 

I understood that there it can be done in three phases:
1. Get Some Idea: `Title`, `Abstract`, and `subsection Titles`, `Important Figure` and `Tables`,
2. Get Overall Idea: `Introduction`, `Conclusion` and Skim through entire text, Leave too much complicated things for now,
3. Get Indepth Idea: Go through Entire Paper to get in depth Understanding, Make **Notes**, **Derive Mathematical Equations** by pen and paper, Get Code and **Implement** Paper, ask question to yourself and have more understanding 


### Distilbert Model Interpretability With Captum
I continued my journey towards model interpretability. I tried `LayerGradientIntergration` method and analysed how each 6 layers of distilbert gives importantance or attribution to input tokens.

Below image shows histogram of importance given to each token at each layers
![image](images/heatmap_distilbert_layers.png)

Below images indicates token name `important` and its attribution value distribution at each layer
![image](images/importance_token_layerwise_attribution.png)
![image](images/distributional_char_of_attribution.png)

[Colab Notebook](notebooks/Distilbert_Model_Interpretability_With_Captum.ipynb)

## Day4:

Started Reading the original researchpaper on [Integrated Gradient - An Axiomatic Attribution for Deep Networks](https://arxiv.org/pdf/1703.01365.pdf) The most interesting thing about this method is. We don't need to modify model, we can simply get Model Interpretability from gradient. 

## Day5:

Completed reading [Integrated Gradient - An Axiomatic Attribution for Deep Networks](https://arxiv.org/pdf/1703.01365.pdf)

In terms of NLP, Integrated Gradient(IG) can be said a path integration of gradient of baseline text to input text. Here, baseline text can be a zero embedding vector. I got a clear picture of the underlining concepts. It's an interesting read to get a theoretical and mathematical understanding of IG.

![equation](images/ig.png)

The underlying concepts and math behindng below awesome heatmap for language traslation is IG
![lang_heatmap](images/language_translation.png)

[Original Implemention Examples](https://github.com/ankurtaly/Integrated-Gradients)

## Day6:

Large language models like GPT3 or GPT-Neo memorize and regurgitate part of their training data. I was exploring how well GPT-Neo model can memorize the pile data. 

Since large language models exhibit minimal overfitting (their train and test losses are nearly identical), we know that memorization, if it occurs, must be a rare phenomenon. I have started knowing more on interpretability of GPT-Neo model in terms of memorization.

[kaggle-data29-notebook](https://www.kaggle.com/usaiprashanth/gpt-1-3b-model)

[with-shuffle](https://github.com/uSaiPrashanth/eleutherai-experiments/blob/main/gpt-1.3b-model-with-shuffling.ipynb)

[without-shuffle](https://github.com/uSaiPrashanth/eleutherai-experiments/blob/main/gpt-1.3b-model-without-shuffling.ipynb)

[eda](https://www.kaggle.com/usaiprashanth/gpt-eda/data?select=results+%285%29)

[Does GPT-2 Know Your Phone Number?](https://bair.berkeley.edu/blog/2020/12/20/lmmem/)

[Euther-AI-Issue](https://github.com/EleutherAI/project-menu/issues/11)

## Day7:

Sometimes we have huge text data or documents which can't fit in the BERT max token length of `512` or similar transformer-based networks. 

We can encode the entire text with a transformer-based network and pass generated embedding to the Autoencoder network. Autoencoder consists of encoder and decoder networks. For text-domain encoder/decoder can be Lstm/GRU. 

This network can remember the large context. It tries to generate combined text representation by also considering the temporal context.

![auto-encoder](images/taper.png)

### How it can  be used for Dimentionality Reduction?

For a given dataset of sequences, an encoder-decoder LSTM is configured to read the input sequence, encode it, decode it, and **recreate** it. The performance of the model is evaluated based on the model's ability to recreate the input sequence.

Once the model achieves a desired level of performance recreating the sequence, the **decoder part of the model may be removed**, leaving just the encoder model. This model can then be used to encode input sequences to a fixed-length vector.

[intro-lstm-autoencoders-blog](https://machinelearningmastery.com/lstm-autoencoders/#:~:text=Autoencoders%20in%20Keras-,What%20Are%20Autoencoders%3F,referred%20to%20as%20self%2Dsupervised.)

## Day8:

Started Working on adding FlaxPegasus Model in Huggingface Transformers

I was suggested to use recently added [cookie clutter templates](https://github.com/huggingface/transformers/tree/master/templates/adding_a_new_model) code that makes the starting model adding code so much easier. Its very fascinating the way it creates sample code for you automatically.

## Day9:

Working on FlaxPegasus Model Code Addition in Huggingface Transformers

I am facing issue while running test cases

## Day10:
Created Pull request for [FlaxPegasus](https://github.com/huggingface/transformers/pull/13420). There are few remaining items. I am working on it.

## Day11:
Fixed one more text case in FlaxPegasus addition and added sinusodial positional embedding in flaxpegasus which makes pegasus model different from Bart model.

## Day12:
Working on fixing `FlaxPegasus` still fixing test case. Made commits to implement suggested changes.

## Day13:
Worked on Fixing `FlaxPegasus` Test case but it did not work out

## Day14:
Fixed `FlaxPegasus` Test cases and the [PR](https://github.com/huggingface/transformers/pull/13420) seems good to go. 1900+ line of code will be added for FlaxPegasus in Huggingface Transformers by me 🥳 
I also found few typos in `FlaxMBart` model will fix in future

## Day15:
I have started reading [Aapraching Almsot any Machine Learning Problem](https://github.com/abhishekkrthakur/approachingalmost/blob/master/AAAMLP.pdf) by Abhishek Thakur

## Day16:
Created [Pull request](https://github.com/huggingface/transformers/pull/13565) with typo fixes for BART based modle in transformers
