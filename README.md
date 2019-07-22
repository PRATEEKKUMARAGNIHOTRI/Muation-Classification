# Classifying Clinically Actionable Genetic Mutations
 
NIPS 2017 comptetion 
<br>
 
Once sequenced, a cancer tumor can have thousands of genetic mutations. But the challenge is distinguishing the mutations that contribute to tumor growth (drivers) from the neutral mutations (passengers). <br>Currently this interpretation of genetic mutations is being done manually. This is a very time-consuming task where a clinical pathologist has to manually review and classify every single genetic mutation based on evidence from text-based clinical literature.<br>So, now the problem is to use this literature and automate the process.

## Data

Click [here](https://www.kaggle.com/c/msk-redefining-cancer-treatment/data) to download the data.

## Summary

The first part of this notebook focused on applying common techniques to preprocess and vectorize free text and evaluate its effectiveness by running them through vanilla Logistic Regression and Random Forest.<br><br>

The techniques used, from least effective to most effective, were:

<br><br>
 * Bag of Words <br><br> 
* TF-IDF <br><br> 
* Word2Vec <br><br>

Because the above approaches did not take into account the temporal patterns in free text, a quick LSTM was tried as well. This approach scored higher than the above without any tuning.

<br><br>In the second part of the notebook, I added the "Gene" and "Variation" features next to the free text features. I tried both label encoding and one-hot encoding, however, the results did not show much improvement.

<br><br>In the third part of the notebook, I generated submissions for both Word2Vec (multiple classifiers) and Keras LSTM and recorded the public leaderboard scores of each submission. The scores were better (around 1) but did not show the same relationships with each other as my own CV (they were mostly close to each other). This is a common occurrence in Kaggle competitions since the public leaderboard is scored on a smaller subset of the test data. Most Kagglers' advice is to ignore the public leaderboard and trust your own CV.