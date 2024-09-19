# Food Poisoning & Restaurant Business Success Prediction

### Author: Rohan B Patel (010745904)

## Introduction

The restaurant industry is one of the largest and fastest-growing sectors, and it faces immense pressure to maintain brand reputation and succeed in a competitive market. This project leverages **Yelp.com** data to address two main objectives:
- **Food Poisoning Prediction**: Identifying businesses likely to cause food poisoning to customers based on reviews.
- **Restaurant Business Success Prediction**: Predicting if a restaurant will succeed based on its location, cuisine type, star rating, and review count.

The project uses various **data mining** and **machine learning** techniques to accomplish these goals.

## Food Poisoning Prediction

### Data Preprocessing
- **Subset of Data**: Selected businesses categorized as "Restaurant" or "Food."
- **Feature Selection**: Merged relevant features from reviews and business data.
- **Stop Word Removal**: Removed common stopwords from the review text.
- **Lemmatization**: Applied WordLemmatizer and `pos_tag` for lemmatizing the review text.

### Data Labeling
- A variable was assigned to review records based on the occurrence of food poisoning-related words and the rating given by the user.

### Algorithms Used
- **Naive Bayes**:
  - Computing Time: 10 seconds
  - Accuracy: 97.4%
- **K-Nearest Neighbors (KNN)**:
  - Computing Time: 15-20 minutes
  - Accuracy: 98.1%

### Data Aggregation
- Restaurants with more than 30% probability of causing food poisoning were flagged. 
- 35 restaurants were classified to have a probability higher than 30%.

### Experimenting with Dataset
- **Decision Tree**, **XGBoost**, and **Random Forest** models were used, but they produced lower accuracy (maximum 50% with XGBoost).

## Restaurant Business Success Prediction

### Data Preprocessing
- Explored features like `stars`, `is_open`, `state`, `city`, `review count`, `categories`, `address`, `longitude`, and `latitude` from the Yelp dataset.
- Analyzed the correlation between cuisine type, location, and star ratings.

### Analysis Performed
- **Cuisine to Stars Correlation**: Explored the relationship between different cuisine types and star ratings.
- **Location to Stars Correlation**: Identified how a restaurant’s location (longitude, latitude, and postal code) affects its success.
- **Clustering**: Applied **DBScan** to cluster nearby restaurants and estimate nearby competitors.

### Models and Accuracy
- **Decision Tree**: 0.65
- **Lasso Regression**: 0.695
- **Gradient Boosted Trees**: 0.75034 (Best accuracy)
- **SVC**: 0.745
- **Random Forest Classifier**: 0.712

### Results
- The best model for restaurant success prediction was **Gradient Boosted Trees**, achieving an accuracy of **75%** when using location and cuisine features.

## Conclusion

This project provides valuable insights for both restaurant owners and customers:
- **Restaurant Owners**: Use the **Restaurant Business Success Prediction** model to make informed business decisions based on customer reviews and location factors.
- **Customers**: Use the **Food Poisoning Prediction** model to identify potential food poisoning risks at a restaurant based on past customer experiences.

For more details, refer to:
- **Project Notebooks**: [Link to notebooks](./project-colab-notebooks/)
- **Project Presentation**: [Link to presentation](./project-presentation/cmpe-255-project-presentation.pdf)
- **Project Report**: [Link to report](./project-report/cmpe-255-final-project-report.pdf)

## How to Run

1. **Clone the repository**:
    ```bash
    git clone https://github.com/rohanbhadreshpatel/restaurant-success-prediction.git
    ```
2. **Navigate to the project directory**:
    ```bash
    cd restaurant-success-prediction/project-colab-notebooks
    ```

3. **Run the Jupyter Notebook or Python scripts**:
    - Open the Jupyter notebook and run the cells in sequence.

## Technologies Used
- **Python** (for data preprocessing, modeling)
- **Naive Bayes**, **KNN**, **Decision Trees**, **XGBoost**, **Random Forest**, **Gradient Boosted Trees**
- **DBScan** for clustering
- **NLP** techniques like **stop word removal** and **lemmatization**

## Acknowledgments

- **Yelp.com** for providing the dataset.
- Special thanks to my project instructor for guidance throughout the project.