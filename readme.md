PROJECT OVERVIEW

Agriculture is essintial in global economy and as the human population grows  their needs to be understanding of global crop yields . This will aid in tackling food security issues and minimizing climate change impacts. 
   

 Problem statements 
 
Project aims to  explore the realioship of differnt factors that affect crop yield specically maize and develop model that predict the yield of maize using this past data according to the realtion ship with factors such as ttemperature rainfall ,area and year 


 Objective

 
    To identifyfactors that affect maize yield
    To develop model that predict maize yiel
    To describe how maize yield is affectd by certain factors


Data understanding

The data has been  exttracted fom kaggle dataset and contains 28243 rows and 7 columns comprising of Area ,item ,year, yield, avrage rainfall ,temperature and pesticide .

Data  Visualization


Data visualization was done using Python’s seaborn and matplotlib libraries to analyze trends and relationships in maize yield across different factors.the  goal is visualizing maize yield relative to different variables, such as area, year, temperature, and rainfall, these plots help in understanding patterns in agricultural production and may serve as an initial analysis for further modeling or prediction.

Plot 1: Maize Yield (hg/ha_yield) vs. Area (Top 10 Areas)

A scatter plot shows the relationship between maize yield and area for the top 10 maize-producing regions.
top_maize_data is the dataset filtered for these top areas.
The x-axis represents the area, while the y-axis represents maize yield in hectograms per hectare.
The plot helps compare the yield across the most productive areas.

Plot 2: Maize Yield (hg/ha_yield) vs. Year

A line plot illustrates the change in maize yield over time.
maize_data is the main dataset containing maize yield values across multiple years.
This plot shows whether there are any trends or fluctuations in yield from year to year.

Plot 3: Maize Yield (hg/ha_yield) vs. Average Temperature

A scatter plot shows the relationship between maize yield and average temperature.
The x-axis represents the average temperature, while the y-axis represents yield.
This visualization explores how yield may be influenced by changes in temperature.


Plot 4: Maize Yield (hg/ha_yield) vs. Average Rainfall

Another scatter plot depicts maize yield against average rainfall per year.
The x-axis represents average rainfall in mm per year.
The plot examines the impact of rainfall on maize production, possibly identifying optimal conditions.

Plot 5: Maize Area vs. Year

A line plot shows how the area dedicated to maize farming changes over time.
This plot provides insight into agricultural trends and potential expansions or reductions in maize cultivation over the years.
Displaying All Plots:

plt.tight_layout() optimizes spacing between subplots for a clean presentation.
Finally, plt.show() renders all plots in a single window.

Data Modelling

Random Forest

This model is designed to predict maize yield based on historical and environmental data.

Check Column Names after One-Hot Encoding:


After applying One-Hot Encoding to categorical columns (e.g., Area), the new column names are printed to verify that each category has been transformed into separate binary columns.
One-Hot Encoding enables the model to interpret categorical data by converting them into a format that can be used in mathematical models.

Feature and Target Variable Selection:

The target variable for prediction is hg/ha_yield, representing maize yield.
X contains all feature columns, including the one-hot encoded columns for Area, and y contains the yield values.
This step ensures that the model learns from all relevant features without including the target variable in the training data.

Splitting the Data:

The dataset is split into training and testing sets using an 80-20 split.
train_test_split ensures that the model is trained on one portion of the data and tested on the other, allowing for an unbiased evaluation of the model’s performance.
The random_state parameter is set to 42 to ensure reproducible results.

Model Initialization and Training:

A Random Forest Regressor is initialized with 100 decision trees (estimators) to make predictions.
The model is trained (model.fit()) on the training data (X_train, y_train), where it learns the relationships between the features and the target variable.

Making Predictions:

The model generates predictions on the test set (X_test) and stores them in y_pred.
These predictions represent the model’s estimate of maize yield based on the input features in the test data.

Model Evaluation:

The model’s performance is evaluated using three metrics:
Mean Absolute Error (MAE): Measures the average absolute difference between predicted and actual yields.
Mean Squared Error (MSE): Indicates the average squared difference, giving more weight to larger errors.
R-squared (R²): Measures how well the model explains the variability in yield; values closer to 1 indicate better performance.
These metrics provide an overview of the model’s accuracy and reliability.

Outputting Evaluation Results:

The code prints the evaluation metrics to the console, allowing quick interpretation of the model’s performance on the test data.

 Neural Network Model
 
 Neural Network model (MLP Regressor) is predicting  maize yield (hg/ha_yield) using features from a dataset (maize_data). Here’s a summary of the key steps and results:

Process Summary
Data Preparation:

Features (X): All columns except the target variable (hg/ha_yield).
Target (y): The maize yield in hectograms per hectare.
The dataset is split into training (80%) and testing (20%) sets.
Model Setup and Training:

MLP Regressor (Multi-Layer Perceptron) is initialized with:
Hidden Layers: 100 neurons in the first layer and 50 in the second.
Activation Function: relu (Rectified Linear Unit), which introduces non-linearity.
Solver: adam, a common optimizer for neural networks.
Maximum Iterations: 500 epochs, or training cycles.
The model is trained on the training data (X_train, y_train).
Predictions and Evaluation:

The model is tested by predicting maize yield for the testing data (X_test).
Performance metrics are calculated to assess accuracy:
Mean Absolute Error (MAE): 9951.85, meaning the predictions deviate by about 9951.85 hectograms per hectare from actual values.
Mean Squared Error (MSE): 197,733,611.27, which highlights the presence of larger prediction errors.
R-squared (R²): 0.7307, indicating that the model explains about 73.1% of the variance in maize yield based on the features.
Summary of Results
While the model achieves a fair R-squared value of 0.7307, suggesting it captures much of the variability in the data, the MAE and MSE are relatively high. This indicates that the model has some accuracy but still produces significant errors, suggesting potential for improvement. Tuning the neural network parameters, adjusting the data, or engineering additional features could enhance performance.


```python
conclusion 
according to the diferent models the r sqaured is abo
```
Recommendations for Enhancing Maize Yield
Based on the analysis, several key factors have been identified that significantly influence maize yield. Here are targeted recommendations to improve yield:

Increase Investment in Pesticides:

The data suggests that regions with higher pesticide usage tend to have improved yields, likely due to better pest control. Increasing pesticide application, while carefully managing environmental impacts, may enhance yield consistency.
Optimize Temperature and Rainfall Conditions:

Temperature and rainfall both exhibit correlations with yield. Locations with moderate rainfall and temperatures around the ideal range for maize growth could potentially maximize yields. It is recommended that farmers consider adaptive practices, such as irrigation management and selecting climate-resilient maize varieties, to buffer against weather fluctuations.
Focus on High-Yield Regions:

Analysis of yield by area indicates some regions consistently outperform others in maize yield. Targeting resources to these high-yield regions, such as Albania, can maximize output. Expanding maize farming in these regions and adopting best practices there could yield the best returns.
Enhance Training and Knowledge Transfer:

Farmers should be trained on best practices around pesticide usage, temperature control techniques (e.g., shade nets), and irrigation systems. Transferring knowledge from high-yield areas to low-yield areas may help underperforming regions improve yields.
Experiment with Advanced Farming Techniques:

Implement precision agriculture technologies, such as soil moisture sensors and climate monitoring tools, to optimize water usage and monitor growing conditions in real time. These tools enable more precise control over environmental variables affecting maize yield.
Continuous Monitoring and Improvement:

Since maize yield is influenced by dynamic factors, continuously monitoring key metrics, such as temperature, rainfall, and pesticide application levels, will help refine the approach each season. Regular data collection and feedback loops can help fine-tune strategies and adapt to changing conditions.
