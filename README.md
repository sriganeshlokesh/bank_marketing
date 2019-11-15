# Bank Marketing

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

Analyzing when clients tend to take term deposit.

## Install
This project is built using Python and the following Python libraries:
- Numpy
- Pandas
- Numpy
- Scikit-Learn
- Seaborn
- Matplotlib
- Missingno

As this is a ipynb file, you will need a software to run the [Jupyter Notebook](https://github.com/sriganeshlokesh/bank_marketing/blob/master/bank_marketing.ipynb)

If Python is not installed on your computer, it is highly recommended to install [Anaconda Distribution](https://www.anaconda.com/distribution/)
The Anaconda Distribution contains all the above packages and more installed.

## Code

The notebook file for this project is `bank_marketing.ipynb`. The model is built using scikit-learn's Random Forest Classifer with the implementation of pipeling.

## Run

In a terminal or command window, run the following commands:
```python
jupyter notebook bank_marketing.ipynb
```
or

```python
ipython notebook bank_marketing.ipynb
```
This will open the Jupyter Notebook software and project file in your web browser.

## Data

Dataset used in this project is [bank-full.csv](https://github.com/sriganeshlokesh/bank_marketing/blob/master/bank-full.csv).
We will using Random Forest Classifier as a base model and apply GridSearchCV to tune the Hyperparameters by consolidating it with pipeling.

#### Features:

1. `age` - Age of Customer

2. `job` - Type of Job(categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')

3. `maritial` - Maritial Status(categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)

4. `education` - Highest Form of Educationcategorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')

5. `default` - Has credit in default?(Categorical: Yes or No)

6. `balance` - Balance in account

7. `housing` - Has a housing loan or not(Categorical: Yes or No)

8. `loan` - Has loan or not(Categorical: Yes or No)

9. `contact` - contact communication type (categorical: 'cellular','telephone')

10. `day` - last contact day of the week (categorical: 'mon','tue','wed','thu','fri')

11. `month` - last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')

12. `duration` - last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). 

13. `campaign` - number of contacts performed during this campaign and for this client (numeric, includes last contact)

14. `pdays` - number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)

15. `previous` - number of contacts performed before this campaign and for this client (numeric)

16. `poutcome` - outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

##### Target Variable:
1. `y` - has the client subscribed a term deposit? (binary: 'yes','no')

### Visualizations

**1. Heatmap**

![Heatmap](https://github.com/sriganeshlokesh/bank_marketing/blob/master/img/Heatmap(Bank).png)

From the above Heatmap we can observe that 
* day and campaign variables are correlated
* age and balance variables are also correlated
When compared to other variables in the dataset, these variables are highly correlated.

**2. ROC-AUC Curve**

![roc_auc](https://github.com/sriganeshlokesh/bank_marketing/blob/master/img/ROC%20AUC%20Curve.png)

The Gridsearchcv model is performing pretty well as compared to the basic model. 

**3. Count plot of Marraige, Education and Contact**

![countplot](https://github.com/sriganeshlokesh/bank_marketing/blob/master/img/Countplot%20(Marraige%2C%20Education%2C%20Cellular%20Contact).png)

From the above plot we have three observations:
* Married couples do not take the term deposit as compared to Single or Divorced couples.
* Secondary educated clients have high chances of not taking the term deposit.
* Clients who are contacted through cellular device tend to decline term deposit.

**4. Count plot of Default, Housing and Loan**

![count_plot](https://github.com/sriganeshlokesh/bank_marketing/blob/master/img/Countplot(default%2Chousing%2C%20loan).png)

* Clients who have credit by default tend to decline term deposit.
* Clients who have housing loan tend to decline term deposit.
* Clients with a loan decline term deposit.

**5. Pairplot**

![pairplot](https://github.com/sriganeshlokesh/bank_marketing/blob/master/img/Pairplot.png)


### Conclusion

The Model has an accuracy of 90.78%.

By applying gridsearch cv with more number of parameter values, we can expect the model to perform much better.


