# Flood Risk Prediction using LightGBM

This repository provides a framework for analyzing flood-related data, generating new features, visualizing relationships, and building a machine learning model for flood probability prediction using LightGBM. Below is an overview of the workflow.

## Key Features of the Code
1. Data Visualization
The code includes visualization functions to better understand the data distribution and relationships between variables:
Numerical Features: plot_numerics(flood_data) generates histograms and boxplots for all numeric features to assess distributions and outliers.
Categorical Features: get_count_plot(cat) creates a bar plot with absolute and relative frequency labels for categorical variables.

2. Correlation Matrix
The correlation between numerical features and the target variable (FloodProbability) is visualized using a heatmap to identify significant relationships.

3. Feature Engineering
A custom function, getFeats(flood_data), generates additional features that provide insights into interactions and statistical properties of the dataset:
Interaction Features:
ClimateAnthropogenicInteraction: Combines climatic and anthropogenic variables to model complex relationships.
InfrastructurePreventionInteraction: Combines variables related to infrastructure and prevention measures.
Statistical Features:
Summary statistics like sum, mean, standard deviation, and kurtosis.
Distribution-related features like percentiles, skewness, and moments.
Novel metrics like harmonic and geometric means, entropy, and coefficient of variation.
The dataset is normalized using StandardScaler to improve model performance.

4. Model Training and Cross-Validation
A LightGBM model is trained using 5-fold cross-validation with custom hyperparameters:
The model is optimized using early_stopping and evaluated based on R² scores for both training and validation sets.
Predictions are averaged across folds to minimize overfitting.

5. Feature Importance
The importance of each feature in predicting flood probability is visualized using LightGBM's built-in feature importance function.

6. Evaluation Metrics
The model's performance is assessed using common regression metrics:

Mean Squared Error (MSE): Measures the average squared difference between predicted and actual values.
Root Mean Squared Error (RMSE): Provides an interpretable error value in the original scale.  
R² Score: Measures how well the model explains the variability in the data.
