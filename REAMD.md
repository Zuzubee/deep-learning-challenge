# Analysis Report

## 1.  Overview:

A nonprofit foundation named `Alphabet Soup` aims to build a deep learning model that can help them to predict whether or not the applicants will be successful for funding. As there are only two categories i.e. successful and not successful, which makes it a binary classification problem. With the dataset provided, the goal is to build a binary classifier that could predict whether applicants will be successful if funded by Alphabet Soup.

## 2. Results

* ### Data Preprocessing:
  * What variable(s) are the target(s) for your model?
    * The *`IS_SUCCESSFUL`* column from application_df is the target variable, this is what we are trying to predict. This shows if the money was used effectively.

  * What variable(s) are the features for your model?
    * **The feature variables we used are:**
      1. `APPLICATION_TYPE`       --> Alphabet Soup application type

      2. `AFFILIATION`            --> Affiliated sector of industry

      3. `CLASSIFICATION`         --> Government organization classification

      4. `USE_CASE`               --> Use case for funding

      5. `ORGANIZATION`           --> Organization type

      6. `STATUS`                 --> Active status

      7. `INCOME_AMT`             --> Income classification

      8. `SPECIAL_CONSIDERATIONS` --> Special considerations for application

      9. `ASK_AMT`                --> Funding amount requested**

  * What variable(s) should be removed from the input data because they are neither targets nor features?
    * The *`EIN`* and *`NAME`* columns are identification columns that typically provide unique identifiers for each organization. These columns usually have no direct impact on the target variable and can be dropped without affecting the model's accuracy.

* ### Compiling, Training, and Evaluating the Model:

  * How many neurons, layers, and activation functions did you select for your neural network model, and why?
    * For this challenge I have implemented `3` different deep learning models, one of them is a simple model while the other two are the optimized versions of deep learning models with a different number of hidden layers, different numbers of neurons, different activation functions, and a different number of epochs.
        ### Simple Neural Network:  
        * The first neural network model named *`simple_model`*, is a two-layer architecture with a specific choice for the number of neurons, layers, and activation functions. By selecting 15 neurons in the first hidden layer (units_1 = 15), 25 neurons in the second hidden layer (units_2 = 25), and using the `ReLU` activation function (activation = "relu") for both hidden layers. The number of epoch for the *`simple_model`* were set to 30. The choice of `ReLU` activation helps introduce non-linearity and allows the model to learn complex relationships between the input features and the target variable. 
        
        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/simple_model.png)

      I used a single neuron in the output layer (units = 1) with a `sigmoid` activation function (activation = "sigmoid") to model the binary classification problem. The sigmoid activation function maps the output to a range between `0` and `1`, representing the probability of the positive class.
        
        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/simple_model_result.png)

        ### Optimized Neural Networks:
     
        * The first neural network model named *`first_model`*, is a two-layer architecture with a specific choice for the number of neurons, layers, and activation functions. By selecting 20 neurons in the first hidden layer (units_1 = 20), 30 neurons in the second hidden layer (units_2 = 30), and using the ReLU activation function (activation="relu") for both hidden layers. The number of epoch for the *`first_model`* were set 50. The choice of `ReLU` activation helps introduce non-linearity and allows the model to learn complex relationships between the input features and the target variable. 

        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/first_model.png)
        
        I used a single neuron in the output layer (units = 1) with a `sigmoid` activation function (activation = "sigmoid") to model the binary classification problem. The sigmoid activation function maps the output to a range between `0` and `1`, representing the probability of the positive class.
        
        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/first_model_result.png)

        * The second neural network model named *`second_model`*, is a three-layer architecture with a specific choice for the number of neurons, layers, and activation functions. By selecting 50 neurons in the first hidden layer (units_1 = 50), 100 neurons in the second hidden layer (units_2 = 100), 200 neurons in the second hidden layer (units_2 = 200), and using the `ReLU` activation function (activation = "relu") for all the hidden layers. The number of epoch for the *`second_model`* were set 75. The choice of ReLU activation helps introduce non-linearity and allows the model to learn complex relationships between the input features and the target variable. 

        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/second_model.png)
        
        I used a single neuron in the output layer (units = 1) with a `sigmoid` activation function (activation = "sigmoid") to model the binary classification problem. The sigmoid activation function maps the output to a range between `0` and `1`, representing the probability of the positive class.
        
        ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/second_model_result.png)
    
  * Were you able to achieve the target model performance?
    
     * As you can see in the third I was only able to achieve 73%, which was not the target model performance which was 75%.

  * What steps did you take in your attempts to increase model performance?
    1.  **Increasing the number of neurons and epochs:**
      * By increasing the number of neurons in a layer, the model becomes more expressive and can capture complex patterns in the data. This allows for better representation of the underlying relationships between the features and the target variable, potentially leading to higher accuracy.
      
      * Increasing the number of epochs gives the model more opportunities to learn from the data and adjust the weights. It allows the model to refine its predictions and find better parameter values, which can lead to improved accuracy. However, it's important to find a balance as increasing epochs excessively can lead to overfitting.
    
    2. Removing only the `EIN` and not the `NAME` column: 
      * In the first neural network i.e. *`simple_model`*, I removed both the `EIN` and `NAME` columns as instructed, which resulted in 73% accuracy, but in the optimization notebook, I only removed the `EIN` column, which helped in improving the accuracy from `73%` to `76%`.
      
     ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/dropping_EIN.png)

     ![Alt text](https://github.com/Zuzubee/deep-learning-challenge/blob/main/images/NAME_value_counts.png)


## 3. Summary:

The model built at the start, without the `EIN` and `NAME` columns, did not perform well and only gave an accuracy of `73%`. In an attempt to optimize the model, or increase the accuracy of the model, when I kept the `NAME` column and also added some extra hidden layers along with increasing the number of neurons, I was finally able to achieve an accuracy greater than `75%`.
