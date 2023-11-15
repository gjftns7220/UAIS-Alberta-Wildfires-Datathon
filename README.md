# UAIS-Alberta-Wildfires-Datathon

**Introduction to the Project**

Welcome to my project page for the Undergraduate Artificial 
Intelligence Society (UAIS) 2023 Alberta Wildfires Datathon.

You can check the official results here:[Leaderboard](https://github.com/UndergraduateArtificialIntelligenceClub/September-2023-Datathon-Submission-Results/tree/main)

**Flowchart Overview**


<img src="https://github.com/gjftns7220/UAIS-Alberta-Wildfires-Datathon/assets/143769164/3d51e171-51f8-419c-bc9f-a98e2abdb9cb" width="500">

**Dataset Description**

The challenge was based on two primary datasets: 'test.csv' and 'train.csv', located in the data folder of this repository. My submission, 'answer.csv', was crafted using the techniques and insights detailed in [MyNotebook](https://github.com/gjftns7220/UAIS-Alberta-Wildfires-Datathon/blob/main/notebook/Alberta_Wildfire_Datathon_Size_Classification.ipynb), which is available for your review.

**Data Cleaning Process**


During the data cleaning stage, I focused on fundamental tasks such as converting all text to lowercase for uniformity and extracting key information from codes, like the fire's area and name. Additionally, I transformed the weather data from mere strings to numerically ordered values through a process called "weather mapping." This was essential to make the dataset more interpretable for the model, ensuring a more accurate representation of the impact of weather conditions on wildfire behavior.

**Time Feature Engineering**

To make the raw date/time data understandable for the model, I employed time feature engineering, primarily focusing on calculating time intervals between key events. This involved creating new features in the dataset, such as 'time_to_discovery', 'time_to_report', 'time_to_dispatch', 'time_to_start_for_fire', 'time_to_assessment', 'time_to_ia_arrival', 'time_to_start_fighting', 'time_to_first_bucket_drop', and 'total_time_to_extinguish'. Each of these features was calculated by subtracting the 'fire_start_date' from other relevant timestamps, using a function compute_time_difference. For example, df['time_to_discovery'] was computed by finding the difference between the 'fire_start_date' and 'discovered_date'. This process was replicated for other critical timestamps, transforming them into more meaningful, model-friendly formats. After creating these new time interval features, I removed the original date columns to streamline the dataset, reducing its size for more efficient training and eliminating less informative data.

**Gaussian Mixture Model & Oversampling**

In my approach to feature engineering, I utilized the Gaussian Mixture Model to uncover complex patterns within the wildfire data, enhancing its interpretability for the predictive model. The Gaussian Mixture Model is a probabilistic model used to represent normally distributed subpopulations within an overall population, ideal for identifying hidden patterns in complex datasets. Additionally, to address the challenge of class imbalance, particularly the underrepresentation of class D & E fires which comprised only 3% of the total cases, I implemented an oversampling strategy. This was essential to mitigate overfitting and bias towards the more common fire classes, thereby improving the model's predictive accuracy for these less frequent but critical wildfire events.

**Model Training and Hyperparameter Tuning & Ensemble Voting Strategy**


In optimizing my models, I utilized Bayesian Optimization for hyperparameter tuning across several algorithms, including CatBoost, XGBoost, Random Forest, and LightGBM. This method, known for its efficiency in finding optimal settings, significantly enhanced model performance by iteratively testing and refining parameters on my training set. Bayesian Optimization is an advanced strategy for efficiently finding the optimal parameters of a function, particularly useful in fine-tuning the hyperparameters of machine learning models. Due to the intensive nature of Bayesian Optimization, this phase was the most demanding in terms of time and computational resources, as it involved multiple runs to fit the best model. Subsequently, I applied an Ensemble Voting strategy, integrating the decisions from each optimized model, to deliver more accurate and reliable final predictions, especially vital in the complex context of wildfire size classification.

