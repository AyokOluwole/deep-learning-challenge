# deep-learning-challenge

**Background** 

The non-profit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With my knowledge of machine learning and neural networks, I created a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.
From Alphabet Soup’s business team, I have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:
•	EIN and NAME—Identification columns
•	APPLICATION_TYPE—Alphabet Soup application type
•	AFFILIATION—Affiliated sector of industry
•	CLASSIFICATION—Government organization classification
•	USE_CASE—Use case for funding
•	ORGANIZATION—Organization type
•	STATUS—Active status
•	INCOME_AMT—Income classification
•	SPECIAL_CONSIDERATIONS—Special considerations for application
•	ASK_AMT—Funding amount requested
•	IS_SUCCESSFUL—Was the money used effectively

 
Steps: 
**Step 1: Preprocess the Data
**
<img width="910" alt="number 1" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/3f4c52e4-1e09-465b-b0b3-f6cdc3020a09">


•	Importing our dependencies and reading the csv

<img width="663" alt="number 2" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/37a9700c-1657-4a82-b02b-49902d42c10a">

•	"EIN" and "NAME" were removed as they did not serve as a guide to whether it would be a success or failure. 
•	Next was to choose a cutoff value and create a list of classifications to be replaced use the variable name `classifications_to_replace`. Replace in dataframe and check to make sure binning was successful.

<img width="535" alt="number 3" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/4d960302-80ac-4e20-9e47-8ef696e3a571">

<img width="838" alt="number 4" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/cf60d90f-9814-4313-8aa5-41659be8dc89">
 

•	Then I used pd.get_dummies() to encode categorical variables.

<img width="536" alt="number 5" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/1cdb8817-1c76-412c-a101-b7de0aeffeca">

•	After, I split the preprocessed data into a features array, X, and a target array, y. And used these arrays and the train_test_split function to split the data into training and testing datasets.

<img width="608" alt="number 6" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/9d5e2575-2cd3-4321-ab2e-70434b5c6ab7">

•	Finally, I scaled the training and testing features datasets by creating a StandardScaler instance, and fitting it to the training data, then used the transform function


<img width="466" alt="number 7" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/2cb4190e-cadd-4f43-899d-49830dcca266">
 
 
 
 
**Step 2: Compile, Train, and Evaluate the Model
**

First, I needed to design a neural network, or deep learning model, to create a binary classification model that can predict if an Alphabet Soup-funded organization will be successful based on the features in the dataset.
•	The first step was to design the neural network model by assigning the number of input features and nodes for each layer using TensorFlow and Keras.
•	Next was to create the first hidden layer and choose an appropriate activation function. And if necessary, add a second hidden layer.
•	Next was to create an output layer and check the structure of the model.



<img width="874" alt="number 8 " src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/24be7653-5f9b-4e70-b74c-83c8abf4c51a">


•	After checking the structure of the model, the next step was to Compile and train the model.

<img width="779" alt="number 9 " src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/7da05c2b-e640-49ea-a961-f40b4ed45de2">

•	Next was to evaluate the model using the test data to determine the loss and accuracy. The accuracy was 72% while loss was 59% 

<img width="628" alt="number 10" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/6a08ddc7-f6a0-4be7-bdf4-dba33d230297">

**Step 3: Compile, Train and Evaluate the Model
**


In compiling, training and evaluating the model, the goal was to achieve a target predictive accuracy higher than 75%. This was done by repeating steps 1 and 2 and adjusting for any modifications that came out of optimizing the model.
•	After repeating the step 1 and 2, the next was to maximize model accuracy. I employed an automated model optimizer that utilizes the keras-tuner library. The optimizer creates a method to generate a keras Sequential model with hyperparameter options, enabling comprehensive exploration for optimal configuration.

<img width="760" alt="number 11" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/d81c1b22-70c6-413f-b801-eae7aa3e02dc">

<img width="750" alt="number 12" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/62d3d3c1-b85a-4c05-8ad1-8a2e0c91cfcb">


•	Before completing the trials, I had to interrupt as the previous load had taken over 3hrs to complete because of the large amount of data.


<img width="712" alt="number 13" src="https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/52804699-6749-4a78-b6c2-7bdde45e00d3">

•	The best model from the keras tuner method achieved 73% prediction accuracy using a sigmoid activation function with input node of 66, 5 hidden layers at a 16, 11, 16, 16, and 26.
•	Next was to evaluate the model to determine the loss and accuracy. The accuracy was 73% while loss was 57% 


Summary: In conclusion, this does not perform well to predict which funding applications are most likely to succeed. When both ran, it has a 73% accuracy was not up to expectation (75%). 



![image](https://github.com/AyokOluwole/deep-learning-challenge/assets/119383340/15eb1f88-b728-4a1a-8e80-680df5d9fac9)
