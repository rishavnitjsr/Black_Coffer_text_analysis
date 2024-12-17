# Black_Coffer_Text_Analysis

<h3>Objective</h3>
Objective of this document is to explain methodology adopted to perform text analysis to drive sentimental opinion, sentiment scores, readability, passive words, personal pronouns and etc.

<h3>Table of Contents</h3>
1	Sentimental Analysis	2
1.1	Cleaning using Stop Words Lists	2
1.2	Creating dictionary of Positive and Negative words	2
1.3	Extracting Derived variables	2
2	Analysis of Readability	3
3	Average Number of Words Per Sentence	3
4	Complex Word Count	3
5	Word Count	3
7	Personal Pronouns	4

<h3>Sentimental Analysis</h3>
Sentimental analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The below Algorithm is designed for use in Financial Texts. It consists of steps:

<h3>Cleaning using Stop Words Lists</h3>
The Stop Words Lists (found in the folder StopWords) are used to clean the text so that Sentiment Analysis can be performed by excluding the words found in Stop Words List. 

<h3>Creating a dictionary of Positive and Negative words</h3>
The Master Dictionary (found in the folder MasterDictionary) is used for creating a dictionary of Positive and Negative words. We add only those words in the dictionary if they are not found in the Stop Words Lists. 

<h3>Extracting Derived variables</h3>
We convert the text into a list of tokens using the nltk tokenize module and use these tokens to calculate the 4 variables described below:

<h4>Positive Score:</h4> 
This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

<h4>Negative Score:</h4>
This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values. We multiply the score with -1 so that the score is a positive number.

<h4>Polarity Score: </h4>
This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 
<h5>Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)</h5>
Range is from -1 to +1

<h4>Subjectivity Score: </h4>
This is the score that determines if a given text is objective or subjective. It is calculated by using the formula: 
<h5>Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)</h5>
Range is from 0 to +1

<h3>Analysis of Readability</h3>
Analysis of Readability is calculated using the Gunning Fox index formula described below.
<h5>Average Sentence Length = the number of words / the number of sentences</h5>
<h5>Percentage of Complex words = the number of complex words / the number of words</h5> 
<h5>Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex words)</h5>

<h4>Average Number of Words Per Sentence</h4>
The formula for calculating is:
<h5>Average Number of Words Per Sentence = the total number of words / the total number of sentences</h5>

<h4>Complex Word Count</h4>
Complex words are words in the text that contain more than two syllables.

<h4>Word Count</h4>
We count the total cleaned words present in the text by 
removing the stop words (using stopwords class of nltk package).
removing any punctuations like ? ! , . from the word before counting.

<h4>Personal Pronouns</h4>
To calculate Personal Pronouns mentioned in the text, we use regex to find the counts of the words - “I,” “we,” “my,” “ours,” and “us”. Special care is taken so that the country name US is not included in the list.

<h4>Average Word Length</h4>
Average Word Length is calculated by the formula:
<h5>Sum of the total number of characters in each word/Total number of words</h5>

