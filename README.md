# heartDisease

This machine learning algorithm takes in a kaggle dataset and predicts the likelihood of an individual having heart disease. 

This is a binary classification - does the person have a diseased heart or not? Because this is a binary classficiation, I used a logistic regression model. Check out the Google notebook [here](https://colab.research.google.com/drive/1NLYbUxVOSe90UCFcw-QMzu41LIwNsW2I?usp=sharing)

I first loaded the csv data to the Pandas dataframe
`heart_data = pd.read_csv('/content/data.csv')`

I then did some standard printing to visualize the dataset, such as printing the first and last five rows
`(heart_data.head(), heart_data.tail())`

I made sure to check for missing values. Luckily, there were none in this dataset. If there were, I would have to use imputation.

Onto the predictive modeling, I started by checking the distribution of the target variable. 0 represents a healthy heart, and 1 represents a diseased heart
`heart_data['target'].value_counts()`
The dataset distribution for the target variable is almost even. If this were not the case, I would need to do some processing.

I then split the features and target to X and Y, respectively. Furthermore, I split the data into training and testing data. Thereafter, I did model training for a Logistic Regression and trained the logistic regression model with training data. After doing this, I did a model evaluation for accuracy score. I tested the accuracy on training data and test data. Both of these numbers were around the same value (training data = 85% accuracy and testing data = 82%). I then built a predictive system using a random persons information from the dataset, excluding their target value. In this instance, I chose 41,0,1,130,204,0,0,172,0,1.4,2,0,2. This individuals target value was 1, meaning they did have a diseased heart. After putting these values in the predictive model, we get a result on 1, meaning the individual has a diseased heart. This is correct given the target given in the dataset.

When building another model like this in the future, I would make sure to incorporate a much larger dataset. This is so that my accuracy scores will be a lot higher. For the size of the used dataset (about 300), an 85% accuracy score is fine, but if trying to publish, or simply looking for a more accurate model, a larger dataset is necessary. 
