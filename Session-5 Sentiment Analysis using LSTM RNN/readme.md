**Assignment**:

1. Look at [this code (Links to an external site.)](https://colab.research.google.com/drive/19wZi7P0Tzq9ZxeMz5EDmzfWFBLFWe6kN?usp=sharing&pli=1&authuser=3) above. It has additional details on "Back Translate", i.e. using Google translate to convert the sentences. It has "random\_swap" function, as well as "random\_delete". 
1. Use "Back Translate", "random\_swap" and "random\_delete" to augment the data you are training on
1. Download the StanfordSentimentAnalysis Dataset from this [link  (Links to an external site.)](http://nlp.stanford.edu/~socherr/stanfordSentimentTreebank.zip)(it might be troubling to download it, so force download on chrome). Use "datasetSentences.txt" and "sentiment\_labels.txt" files from the zip you just downloaded as your dataset. This dataset contains just over 10,000 pieces of Stanford data from HTML files of Rotten Tomatoes. The sentiments are rated between 1 and 25, where one is the most negative and 25 is the most positive.
1. Train your model and achieve **60%+ validation/text accuracy**. Upload your collab file on GitHub with readme that contains details about your assignment/word (minimum **250 words**), **training logs showing final validation accuracy, and outcomes for 10 example inputs from the test/validation data.**

**Approach:**

<https://pypi.org/project/pytreebank/> The Stanford sentiment analysis dataset is imported from pytreebank 

![Dataset Vocabulary](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/vocabulary.png)

**Model** 

![Model Parameters](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/model_param.png)

**Augmentation**:

When we augmented data for 0th and 2nd class and added 500 samples for each class with backtranslation and keyword, ORC based augmentation using NLPAUG.

**Back translation**: The sentences are converted to a random language using google translate and converted back to English to get similarly structured sentence.

![English to german](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/english_german.png)

![German to english](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/german_to_english.png)

**KeywordAug**: Augmenter that simulates typo error by random values. For example, people may type ‘I’ as ‘o’ incorrectly. One keyword distance is leveraged to replace character by possible keyboard error.

**ocrAUg**: Augmenter that simulates OCR error by random values. For example, OCR may recognize I as 1 incorrectly. Pre-defined OCR mapping is leveraged to replace character by possible OCR error.

**Results and Accuracy**:
![accuracy curve without augmentation](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/without_augmentation.png)
![accuracy curve with augmentation](https://github.com/JahnaviRamagiri/END2.0/blob/main/Session-5%20Sentiment%20Analysis%20using%20LSTM%20RNN/images/with_augmentation.png)




