# Quora_Project_NLP
It is a kaggle competetion problem where we have to classifiy the given two questions are duplicate or not. in the given dataset there are only 4 columns. With these columns i have applied the basic preprocessing steps, then applied RandomForest and XGBoost algorithms. I got an accuracy of 68%. Then I have done the feature extraction and added 8 more features(like each question_length, common_words, each no. of words,,etc)  to the dataset. Then i got an accuray of 72 %. After seeing the top accuracy in kaggle leaderborad. I thought to perform advanced Feature extraction(like Fuzzy features) and added more 15 columns to the dataset. Finally got an accuracy of ~80%. 

## Advanced Feature engineering
### 1. Token Features
cwc_min: This is the ratio of common words to minimum length of words between questions.

cwc_max: bold text This is the ratio of common words to maximum length of words between questions.

csc_min: This is the ratio of the number of common stop words to the minimum stop word length between the questions.

csc_max: This is the ratio of the number of common stop words to the maximum stop word length between the questions.

ctc_min: This is the ratio of the number of common token to minimum token count between the questions.

ctc_max: This is the ratio of the number of common token to maximum token count between the questions.

last_word_eq: 1 if the last word in the two questions is same, 0 otherwise.

first_word_eq: 1 if the first word in the two questions is same, 0 otherwise.

### 2. Length Based Features
mean_len: Mean of the length of the two questions(number of words)

abs_len_diff: Absolute difference between the length of the two questions(number of words)

longest_substr_ratio: Ratio of the length of the longest substring among the two questions to the length of the smaller question

### 3. Fuzzy Features
fuzz_QRatio: fuzz_ratio is the similarity score based on leveshitein distance.
Levenshtein distance: measures the minnimum number of single=character edits( insertions, delections, or substitutions) required to transform one string into another.

fuzz_ratio: It is 90% same as fuzz_qratio but it is case sensitive(uppercase vs lowercase). below is the example

fuzz_partial_ratio: is a way to measure how similar two strings are by considering the best matching part between them.It's like finding the most similar part in both the sentences.

token_sort_ratio: is a way to measure how similar two strings are after sorting the words in each string. I works by tokenizing the sentences into words, sorting the words in each sentence, and then calculating the similarity between the sorted sentences.

token_set_ratio: measures the similarity between two sentences based on their token sets, considering common words while allowing for differences in word order, missing words, or repeated words.

