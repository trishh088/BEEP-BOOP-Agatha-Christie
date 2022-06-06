# <p align="center">***BEEP BOOP Agatha Christie?***</p>

<p align="center">
  <img width="300" height="300" src="https://static.vecteezy.com/system/resources/thumbnails/006/777/102/small_2x/the-mascot-of-cute-ballpoint-as-a-detective-vector.jpg">
</p>

<p align="center">(Gutenberg Sequence-to-Sequence Generator)</p>

Recurrent Neural Networks can be used as generative models and that is exactly what I was trying in this project. I used three public domain books by Agatha Christie, from Project Gutenberg, to train a sequence-to-sequence model to generate the first page of a non-existent book. I fed sentences from several of her books and then demonstrated the capability of the model to generate new sentences. Several models were tested to generate the one-pager.

The notebook follows a pattern of first using "The Mysterious Affair at Styles.txt" to generate text using character-based modeling to generate text (I first tried to generate only 1000 characters to test our model generation and then once I selected the model, I generated 5000 words to get content/words worth calling "page generation"). Throughout the notebook, code has been explained wherever possible or needed. I have used the code and the explanation by Jason Brownlee(mentioned in the references section) as a base for the modeling and then built on it.

After using the book "The Mysterious Affair at Styles.txt", I added books "POIROT INVESTIGATES.txt" and "The Murder on the Links.txt" in an attempt to add more data for the model to learn, along with building better LSTM models to reduce the loss and improve the predictions. I also tried to use a Bidirectional LSTM to see if we can get a better prediction(here I tried to use words rather than characters to generate text).

There are two notebooks due to the limitation of running them on free resources on Colab and Kaggle. The sequence to read the notebooks is as follows:
1) [Notebook 1](https://github.com/trishh088/BEEP-BOOP-Agatha-Christie/blob/2d835484e567a20689e37d9e2335efa9eb61139b/Sequence%20generation%20notebook_1.ipynb)
2) [Notebook 2- Using Bidirectional LSTM](https://github.com/trishh088/BEEP-BOOP-Agatha-Christie/blob/2d835484e567a20689e37d9e2335efa9eb61139b/Sequence%20generation%20notebook_2_(Bidirectional_LSTM).ipynb)

# Conclusion
I first removed the header and footer of books which I extracted from the Gutenberg website. Then I extracted the book, made it lower case (to reduce the number of characters for our model to learn), broke down the words into characters, and took a set of it to remove duplicates. I then created different models to train our data by changing the input lengths - (the number of books we used to train) and how many characters I used to train the model on, the batch size, and epochs. Due to limitations of colab/kaggle and Juypterhub, the notebook kept crashing randomly so I used model checkpoint to record all of the network weights to file each time an improvement in the loss was observed at the end of each epoch. I used the best set of weights (lowest loss) to instantiate our generative model. Eventually, I saw that using character-generated models can't make good predictions and despite constantly reducing the loss, the predictions didn't make sense. Then I moved on to create a model that was trained on words rather than characters and despite having a loss of 3.35, the data predicted by the bidirectional model was far better. The only shortcoming of the model was that it didn't capitalize proper nouns (which it couldn't learn as I made all the words lower case before tokenizing) and if I had more compute capability(probably purchasing a pro version for RAM, CPU, and GPU), I could work on making a better model which would generate sentences that not only make sense but also follow all the grammatical rules that exist in the English language. All the models saw that the loss was reduced with each good epoch and we were sure that there is no overfitting in our models.
Below is a table that has summarized all the model's results:

![image](https://user-images.githubusercontent.com/30213777/172081838-b8678559-c60c-48f6-86c0-9b4807a8948a.png)


# Acknowlegment 
This project was my final project for Natural Language Processing subject and I would like to take this opportunity to thank Prof Jeffrey M. Stanton, for helping me throughout the semester with so many of my doubts and for being a mentor in my journey of Applied Data Science be it through videos for Quantitative Reasoning for Data Science or Natural Language Processing.

I would also like to thank Jason Brownlee for his article on machinelearningmastery.com

# References:

1) Image - https://www.vecteezy.com/vector-art/6777102-the-mascot-of-cute-ballpoint-as-a-detective

2) https://machinelearningmastery.com/text-generation-lstm-recurrent-neural-networks-python-keras/

3) https://stackoverflow.com/questions/40761185/what-is-the-intuition-of-using-tanh-in-lstm

4) https://www.analyticsvidhya.com/blog/2018/03/text-generation-using-python-nlp/

5) https://github.com/pranjal52/text_generators/blob/master/a_gigantic_model.ipynb

6) https://towardsdatascience.com/nlp-text-generation-through-bidirectional-lstm-model-9af29da4e520
