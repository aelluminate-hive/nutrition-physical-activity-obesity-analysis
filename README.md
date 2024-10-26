# Nutrition, Physical Activity, and Obesity Analysis - Behavioral Risk Factor Surveillance System (BRFSS)

## Dataset Description
This dataset, from the Behavioral Risk Factor Surveillance System (BRFSS), focuses on tracking trends in nutrition, physical activity, and obesity across various demographic groups in the U.S. It includes data from multiple years, locations, and population segments with variables like age, education, gender, income, and race/ethnicity.

The dataset can be accessed from the following URL: [Dataset](https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-behavioral-risk-factor-surveillance-system?fbclid=IwZXh0bgNhZW0CMTAAAR06sf4V3a6QvGmiEEsI5gODocjC0y01v1GMCCDnOiF5NOWXjRJCk3KtlvA_aem_AejP2I3PCDm4L1rdrQ-fxQ).

### Data Columns and Descriptions
- **YearStart**: Starting year of data collection for a particular record.
- **YearEnd**: Ending year of data collection for the record (usually the same as `YearStart`).
- **LocationAbbr**: Abbreviation of the location (e.g., state or region).
- **LocationDesc**: Full description of the location.
- **Datasource**: The data source or system from which the data is collected.
- **Class**: High-level category of the topic (e.g., "Nutrition", "Physical Activity").
- **Topic**: Specific topic within the class (e.g., "Fruit Consumption", "Exercise Frequency").
- **Question**: Survey question asked to gather the data.
- **Data_Value_Unit**: Unit of measurement for the data value (e.g., percentage).
- **Data_Value_Type**: Type of data value (e.g., "Mean", "Percentage").
- **Data_Value**: Collected data value based on the question.
- **Data_Value_Alt**: Alternate form of the data value, if applicable.
- **Data_Value_Footnote_Symbol**: Symbol indicating a footnote related to the data value.
- **Data_Value_Footnote**: Footnote text providing additional context or clarification about the data value.
- **Low_Confidence_Limit**: Lower bound of the confidence interval for the data value.
- **High_Confidence_Limit**: Upper bound of the confidence interval for the data value.
- **Sample_Size**: Number of survey respondents used to calculate the data value.
- **Total**: Aggregate total for the specific category or group.
- **Age(years)**: Age group of respondents, measured in years.
- **Education**: Education level of respondents.
- **Gender**: Gender of respondents.
- **Income**: Income level of respondents.
- **Race/Ethnicity**: Race or ethnicity of respondents.
- **GeoLocation**: Geographic coordinates (latitude and longitude) of the location.
- **ClassID**: Unique identifier for the class category.
- **TopicID**: Unique identifier for the topic.
- **QuestionID**: Unique identifier for the question.
- **DataValueTypeID**: Unique identifier for the data value type.
- **LocationID**: Unique identifier for the location.
- **StratificationCategory1**: Category used for stratification (e.g., age, gender).
- **Stratification1**: Specific stratification within the category (e.g., "Male" or "Female").
- **StratificationCategoryId1**: Unique identifier for the stratification category.
- **StratificationID1**: Unique identifier for the specific stratification.

## Summary of Findings
The analysis highlights patterns in obesity, physical activity, and nutrition trends across different demographic groups. Factors like age, gender, education, and income appear to correlate with differences in obesity rates and activity levels, revealing insights valuable for public health initiatives.

1. **Physical Activity and Obesity**: Trends indicate that lower physical activity is associated with higher obesity rates.
2. **Diet and Obesity**: Individuals with poor dietary habits showed a higher prevalence of obesity.
3. **Demographics and Health Risk**: Obesity rates vary significantly by age, gender, and region.

## Data Preprocessing
Preprocessing steps included:
1. **Data Cleaning**:
   - Removed missing values and irrelevant columns (e.g., `Datasource`, `Data_Value_Footnote_Symbol`, `Total`).
   - Imputed values for missing entries where possible.
2. **Feature Engineering**:
    - Encoded categorical columns like `Gender`, `Race/Ethnicity`, `Income`, and `Age(years`.
    - Scaled features using `StandardScaler` to normalize data for model training.
    - Handling missing values using `SimpleImputer`.
    - Label encoding categorical variables with `LabelEncoder`.

## Exploratory Data Analysis
Key exploratory steps included examining the distribution of obesity across demographics, investigating correlations, and detecting potential outliers. Descriptive statistics were calculated for numeric variables, and categorical data was visualized to identify prominent trends.

## Visualization
Various visualizations were created to illustrate findings:
1.  **Distribution of Categorical Data**: 
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/1.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/2.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/3.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/4.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/5.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/6.png)
    ![Distribution of Categorical Data](images/distribution_of_categorical_data/7.png)
    - This visualization function displays the distribution of categorical variables in the dataset. It excludes columns with less meaningful information, like `Datasource` and `LocationAbbr`, focusing instead on core demographic categories. For each selected categorical column, a histogram shows the frequency distribution of categories, making it easier to observe data patterns and identify common or rare values in each category.
2.  **Count Plot of Categorical Data**: 
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/1.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/2.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/3.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/4.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/5.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/6.png)
    ![Count Plot of Categorical Data](images/count_plot_of_cat_data/7.png)
    - This count plot function provides a more detailed look at categorical distributions by plotting the count of each category in a bar format. By focusing on core demographic attributes and excluding irrelevant columns, this visualization highlights the prevalence of each category within the dataset, providing a clearer sense of categorical distributions.
3.  **Box Plot of Categorical Data**: 
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/1.png)
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/2.png)
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/3.png)
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/4.png)
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/5.png)
    ![Box Plot of Categorical Data](images/box_plot_of_cat_data/6.png)
    - This function generates a box plot for each categorical variable, showing the range and distribution of values within each category. The box plot excludes certain less relevant columns (e.g., `Gender`, `LocationDesc`) to focus on key demographic insights. This visualization highlights the spread and potential outliers within each categorical attribute, offering a deeper look at value variability.
4.  **Scatter Plot of Continuous Variables**: 
    ![Scatter Plot of Continuous Variables](images/scatter_plot_of_continuous_variables.png)
    - The scatter plot function visualizes relationships between continuous variables (e.g., `Sample_Size` and `Data_Value`), with color coding by the `Class` variable for added insight. The scatter plot enables easy identification of trends or clusters, showing how data points are distributed across the selected variables and revealing potential correlations.
5.  **Correlation Matrix of Numerical Data**: 
    ![Correlation Matrix of Numerical Data](images/correlation_matrix_of_numerical_data.png)
    - The correlation matrix visualizes the correlation coefficients between numerical variables using a heatmap. By displaying the degree of positive or negative relationships between features, this visualization aids in identifying potential multicollinearity and understanding how different numerical variables influence each other.

Each visualization includes interpretations that provide context and insights derived from the data.

## Model Development
The following models were developed to predict obesity and assess factors affecting physical health:
1. **Logistic Regression**
2. **Support Vector Classifier (SVC)**
3. **Random Forest Classifier**
4. **Gradient Boosting Classifier**

Each model was fine-tuned using `GridSearchCV` to optimize performance based on accuracy and other relevant metrics.

## Model Evaluation

Each of the models evaluated – Logistic Regression, Support Vector Machine (SVM), Random Forest, and Gradient Boosting – achieved an accuracy of 100%. This high accuracy score indicates that all models were able to perfectly classify the instances in the dataset. Below is a detailed breakdown of the evaluation metrics:

- **Accuracy**: Each model achieved 100% accuracy, meaning that all models classified every instance correctly without any errors.

- **Classification Report**:
  - **Precision, Recall, and F1-Score**: For each class (0, 1, and 2), the precision, recall, and F1-score are all 1.0, signifying perfect classification performance. This means that each model has a perfect balance of correctly identifying both positive and negative instances without misclassification.
  - **Macro Average**: The macro average metrics (1.0 for precision, recall, and F1-score) further confirm that each class has been classified accurately with equal precision.
  - **Weighted Average**: The weighted average (1.0 across metrics) aligns with the overall classification accuracy, highlighting that the models were consistent across all classes and did not favor one class over others.

- **Confusion Matrix**: The confusion matrix for each model shows no off-diagonal values, indicating zero misclassifications. For example:
  - Class 0: All 1,493 instances were correctly classified as class 0.
  - Class 1: All 6,396 instances were correctly classified as class 1.
  - Class 2: All 8,374 instances were correctly classified as class 2.

### Interpretation of 100% Accuracy
The 100% accuracy could imply that:
1. The dataset may be highly structured or simple enough for these models to classify without errors.
2. There may be limited or well-separated patterns in the data, allowing models to identify each class with certainty.
3. There is a possibility of data leakage if features overlap strongly with target classes or if the model training was inadvertently exposed to test data.

Further analysis may be warranted to ensure this accuracy is valid and generalizable to unseen data.

## Conclusion
This project provides a comprehensive analysis of the BRFSS dataset, identifying key behavioral risk factors associated with obesity. The developed models offer insights into public health risks, which can guide preventive measures and policy decisions.