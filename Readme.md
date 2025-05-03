# Instagram Fake Account Detection

This project uses machine learning to classify Instagram accounts as either genuine or fake/spammer accounts. It utilizes a Random Forest Classifier to analyze various features of user profiles and predict their authenticity.

## Overview

The notebook performs the following steps:

1.  **Data Loading:**
    * Loads the dataset from a CSV file named `train.csv`.
    * Prints the column names to understand the data structure.

2.  **Exploratory Data Analysis (EDA):**
    * **Initial Data Check:**
        * Prints the number of missing values for each feature to identify any data completeness issues.
        * Prints descriptive statistics of the dataset (e.g., mean, standard deviation, min, max) to understand the distribution and range of values for each feature.

3.  **Model Training and Evaluation:**
    * **Data Preprocessing:**
        * (Note: The provided code snippet doesn't show explicit preprocessing steps, but in a complete project, this section would handle tasks like feature scaling, encoding categorical variables, or handling outliers if necessary.)
    * **Feature and Target Separation:**
        * Separates the features (X) from the target variable (y), where 'fake' is the target indicating whether an account is fake (1) or genuine (0).
    * **Data Splitting:**
        * Splits the data into training and testing sets (80% for training, 20% for testing) using `train_test_split` with a `random_state` for reproducibility.
    * **Model Building:**
        * Initializes and trains a Random Forest Classifier model with 100 estimators (`n_estimators=100`) and a `random_state` for reproducibility.
    * **Model Evaluation:**
        * Predicts the class labels for the test set.
        * Prints a classification report (`classification_report`) to evaluate precision, recall, F1-score, and support for each class.
        * Prints the confusion matrix (`confusion_matrix`) to visualize the number of correct and incorrect predictions.
        * Prints the accuracy score (`accuracy_score`) to measure the overall correctness of the model.
        * Visualizes the confusion matrix using `ConfusionMatrixDisplay` for better interpretability.

## Dataset

The dataset used for this project is `train.csv`. It contains features related to Instagram user profiles, including:

* `profile pic`: Indicates the presence of a profile picture.
* `nums/length username`: Ratio of numeric characters to the length of the username.
* `fullname words`: Number of words in the full name.
* `nums/length fullname`: Ratio of numeric characters to the length of the full name.
* `name==username`: Whether the full name is the same as the username.
* `description length`: Length of the profile description.
* `external URL`: Indicates the presence of an external URL.
* `private`: Indicates if the account is private.
* `#posts`: Number of posts.
* `#followers`: Number of followers.
* `#follows`: Number of accounts followed.
* `fake`: Target variable (1 for fake, 0 for genuine).

## Libraries Used

* pandas
* numpy
* scikit-learn (sklearn)
* seaborn
* matplotlib.pyplot

## Usage

To run this code:

1.  Ensure you have Python 3.x installed.
2.  Install the required libraries:

    ```bash
    pip install pandas numpy scikit-learn seaborn matplotlib
    ```

3.  Place the `train.csv` file in the same directory as your Python script or Jupyter Notebook.
4.  Run the script or notebook.

The script will:

* Load the data.
* Perform EDA.
* Train the Random Forest model.
* Evaluate the model's performance.
* Print the classification report, confusion matrix, and accuracy.
* Display the visualized confusion matrix.

## Potential Improvements

* **Feature Engineering:** Create new features or transform existing ones to potentially improve model performance.
* **Data Preprocessing:** Implement robust data preprocessing techniques, including scaling, handling categorical features, and outlier detection.
* **Hyperparameter Tuning:** Optimize the hyperparameters of the Random Forest model (e.g., `n_estimators`, `max_depth`, `min_samples_split`) using techniques like GridSearchCV or RandomizedSearchCV.
* **Model Selection:** Experiment with other classification models (e.g., Logistic Regression, Support Vector Machines, Gradient Boosting) to compare performance.
* **Cross-Validation:** Use cross-validation to obtain more reliable estimates of model performance.
* **Further Visualization:** Create additional visualizations to explore relationships between features and the target variable.
