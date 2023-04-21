# ML-and-GANs
The models were trained on a AMD Ryzen 7 1700 Eight-Core Processor. The codes are written in python using Jupyter Notebook.
==================================================================================
Data
*****
Raw Data downloaded from kaggle (https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction):
train.xlsx
test.xlsx

Some simple preprocessings were made manually in excel:
airline_train_BlanksRemoved.xlsx 
airline_test_BlanksRemoved.xlsx  

Syn_data.xlsx is the data generated by our code (explained in the next part)
==================================================================================
The project contains 2 main codes.
1- GAN: Produce the GAN network and the syntethic data.
2- ML: Testing different data (syntethic, real, combined) on different ML models.
-----------------------------------------------------------------------------------
GAN
*****
a) Run Libraries section

b) Run Importing Data section: change the dirrectory to r'YOUR-ADRESS/FILE-NAME.xlsx'. 
	df is the train data: airline_train_BlanksRemoved.xlsx
	in the last line we have computed the norm of the data, we will use this matrix norm in the "Evaluating Different ML models" part
	you can see the matrix norms (we use it in the next code)

b) Run Functions section: you can change the NN parameters to see the differences they can make.

d) Run Training & Producing fake data for discriminator: you can change the number of fake data produced to train the discriminator by the variable n. and finally you can see the accuracy.
	Note: by runing the whole section once you have a discriminator model. For a valid evaluation on the fake data, produce a new set of fake data by running the second subsection again (ignore the 1st and the 3rd subsections) and run the last subsection to see the accuracy on fake and real data.

e)Run Training GAN section:
	1: a summary of the model that have not been trained yet
	2: training the gan
	3:a summary of the trained model 

f)Run Generating Data section: 
	1:by changing the the value 10001 to n, you generate n synthetic data.
	2: it exports the synthetic data to your computer (where you run the code)
-----------------------------------------------------------------------------------
Evaluating Different ML models 
*****
a) Run Libraries section

b) Run Functions section: define a global variable A manually as the norm of your train data features (obtained in GAN part)

c) Run Importing Data section: change the 3 dirrectories to r'YOUR-ADRESS/FILE-NAME.xlsx'. 
	df1 is the test data: airline_test_BlanksRemoved.xlsx
	df2 is the original train data: airline_train_BlanksRemoved.xlsx
	df3 is the synthetic train data: Syn_data_good.csv

d) Run Training and Evaluating section: You can see the different models used in subsections:
	SVM : RBF,Linear,sigmoid: each model were trained and tested on combined, syntethic in each subsection and the accuracy is reported.

	KNN : k=3,k=5,k=7: each model were trained and tested on combined, syntethic in each subsection and the accuracy is reported. you can simply change the value n_neighbors in order to change k.


	Neural Networks: model1,model2: each model were trained and tested on combined, syntethic in each subsection and the accuracy is reported. You can change the S_NN1 layers for different NNs to see what differences it can make.
===================================================================================
Table.xls is the model accuracies obtained by our evaluation.
