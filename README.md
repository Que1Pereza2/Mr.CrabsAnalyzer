# Mr.CrabsAnalyzer
The second part of the Python AI used to analyze comments's feelings.

1. Adquire the Data
	We will use the CSV from the part 1 that is filled with the scores and reviews,

2. Data preprocessing
	Clean the data before starting to manipulate it by removing punctuation marks, accents etc.

2.1. Text numeric representation 
	The AI only understands numbers so we have to represent the text with numbers, for this we have 2 ways to go about it
Bag of Words and TF-IDF.
	
  Bag of Words
		It's the simplest way of representing text with numbers, it takes the words and all of the words and 
places them in an array without duplicating them and feeding them to the AI with 0's in place of the words that don't appear in the prompt and 1 for the words that do appear.

  example:
		p1:"I like cats."
		p2:"They are liquid."
		p3:"Cats are liquid."
			
  array [i, like, cats, they, are, liquid]
			
  prompt:"I like liquid"
			
  AI prompt [1, 1, 0, 0, 0, 1]
	
   TF-IDF
		This way of passing the data to the AI is similar to bag of words, but depending on the frequency of each word they are assigned different weights. To calculate this weight we need two variables TF and IDF.
			TF = (times a word is repeated in a document)/(total words in the document)
			IDF = log((total number of documents)/(number of documents that contain that word))
		to get the word's weight we simply subtract IDF from TF.

3. Neuronal Network design model
	We will use scikit-learn to implement a NN model, the design will include choosing an architecture, activation function and other hyperparameters.
	
	Choosing an algorithm should be based on a few elements, the data set, the text type and the computation power available.
	Some of the most common algorithms are:
	
	  Logic Regression: a simple algorithm but effective at binary and multiclass classification.
			https://www.bioestadistica.uma.es/apuntesMaster/regresi%C3%B3n-log%C3%ADstica-binaria.html

	  Naïve Bayes: these classifiers are often used in feelings classification.
			https://www.jacobsoft.com.mx/es_mx/clasificador-naive-bayes/
		
	  Random Forest: these classifiers are a good choice when working with moderate to big text data.
			https://www.datacamp.com/tutorial/random-forests-classifier-python

4. Training and Model Evaluation
	The data set will be separated in training and testing data.
	The most common testing metrics used are precision, recall, and F1-score.
	
	precision - measures the correct predictions compared to all the predictions made.
	recall - measures the only the correct positive cases compared to what the model identified as possitive.
	F1-score - combines precision and recall in one metric.

5. Error analysis
	Model errors will be analysed in order to improve the model.

6. Results
	The model's results will be presented with the evaluation metrics and examples of successful and unsuccessful predictions.
