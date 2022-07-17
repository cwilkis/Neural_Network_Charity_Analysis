# Neural_Network_Charity_Analysis

## Overview of Prediction Risk Analysis

The purpose of this project was to assess investments in different charities using neural networks with tensorflow platform in Python. The main asks were to : 
	- Process the data for the neural network model
	- Compile, train, and evaluate the model
	- Optimize the model to increase accuracy above 75%

## Results

### Data Processing
	- Variables considered targets
		- Is_Successful column
	- Variables considered features
		- Affiliation
		- Application_Type
		- Ask_type
		- Classification
		- Income_Amt
		- Is_Successful
		- Orginization
		- Status
		- Special_consideration
		- Use_Case
		
	- Variables to be removed
		- EIN and Name for initial analysis and for two of the optimization attempts

### Compiling, Training, and Evaluating the Model

	- Neurons, layers, and activation functions 
		- Input Layer had the length of x_train (number of features)
		- Hidden Layer 1 had 80 neurons with a relu Activation Function
		- Hidden Layer 2 had 30 neurons with a relu Activation Function
		- Output Layer used a sigmoid Activation Function

	- Activation function for hidden layers chosen was relu due to it being ideal for nonlinear input data
		- Sigmoid chosen for Output Layer as it is ideal for binary classification
		- Layer 1 neurons was determined to be 80, or roughly twice the input features
		- Layer 2 neurons w determine to be 40, or roughly 1 times the input features bringing the total to 3 times the input features
	
	- Target model performance
		- Initial performance 72.5% 
		![This is an image](https://github.com/cwilkis/Neural_Network_Charity_Analysis/blob/main/Images/Initial%20Build.png)

		- Optimization Attemp 1 63.1% 
		![This is an image](https://github.com/cwilkis/Neural_Network_Charity_Analysis/blob/main/Images/Optimization%201.png)

		- Optimization Attempt 2 72.6%
		![This is an image](https://github.com/cwilkis/Neural_Network_Charity_Analysis/blob/main/Images/Optimization%202.png)

		- Optimization Attempt 3 78.1%
		![This is an image](https://github.com/cwilkis/Neural_Network_Charity_Analysis/blob/main/Images/Optimization%203.png)

	- Steps taken to increase model performance
		
		- Attempt 1: Dropped affiliation and orignization columns and set # of epochs to 150
		- Attempt 2: Added a third hidden layer and increased # epochs to 150
		- Attempt 3: kept NAME column and separated into buckets using <10 as the criteria

## Summary

Optimizng the model by grouping the Name column increased the accuracy of the model. Dropping different columns decreased the accuracy, and adding a hidden layer did not significantly change the accuracy. 

I recommend also using a supervised machine learning model, specifically the random forest classifier. This model combines different data sample sets to generate a classified output and can evaluate the performance against this neural network model. 