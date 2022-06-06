# <p align="center">***BEEP BOOP Agatha Christie?***</p>

<p align="center">
  <img width="300" height="300" src="https://static.vecteezy.com/system/resources/thumbnails/006/777/102/small_2x/the-mascot-of-cute-ballpoint-as-a-detective-vector.jpg">
</p>

<p align="center">(Gutenberg Sequence-to-Sequence Generator)</p>

Recurrent Neural Networks can be used as generative models and that is exactly what we will be trying in this project. We are using three public domain books by Agatha Christie, from Project Gutenberg, to train a sequence-to-sequence model to generate the first page of a non-existent book. We are feeding sentences from several of her books and then demonstrating the capability of our model to generate new sentences. Several models have been tested to generate the page.

The notebook follows a pattern of first using "The Mysterious Affair at Styles.txt" to generate text using character-based modeling to generate text (we have first tried to generate only 1000 characters to test our model generation and then once we select our model we will generate 5000 words to get content/words worth calling "page generation"). Throughout the notebook, code has been explained wherever possible or needed. We have used the code and the explanation by Jason Brownlee(mentioned in references section) as a base for our modeling and then built on it.

After using one book we have added books "POIROT INVESTIGATES.txt" and "The Murder on the Links.txt" in an attempt to add more data for our model to learn, along with building better LSTM models to reduce our loss and improve our predictions. We have also tried to use a Bidirectional LSTM to see if we can get a better prediction(here we tried to use words rather than characters to generate text).

There are two notebooks due to limitation of running them on free resources on Colab and Kaggle. The sequence to read the notebooks are as follows:


I would like to take this opportunity to thank Prof Jeffrey M. Stanton, for helping me throughout the semester with so many of my doubts and for being a mentor in my journey of Applied Data Science be it through videos for Quantitative Reasoning for Data Science or for Natural Language Processing.
