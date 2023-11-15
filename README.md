# UAIS-Alberta-Wildfires-Datathon

Welcome to my project page for the Undergraduate Artificial 
Intelligence Society (UAIS) 2023 Alberta Wildfires Datathon.

You can check the official results here:[Leaderboard](https://github.com/UndergraduateArtificialIntelligenceClub/September-2023-Datathon-Submission-Results/tree/main)

**Flowchart**


![image](https://github.com/gjftns7220/UAIS-Alberta-Wildfires-Datathon/assets/143769164/3d51e171-51f8-419c-bc9f-a98e2abdb9cb)

**Dataset**

The challenge was based on two primary datasets: 'test.csv' and 'train.csv', located in the data folder of this repository. My submission, 'answer.csv', was crafted using the techniques and insights detailed in [MyNotebook](https://github.com/gjftns7220/UAIS-Alberta-Wildfires-Datathon/blob/main/notebook/Alberta_Wildfire_Datathon_Size_Classification.ipynb), which is available for your review.

**Data Cleaning**


During the data cleaning stage, I focused on fundamental tasks such as converting all text to lowercase for uniformity and extracting key information from codes, like the fire's area and name. Additionally, I transformed the weather data from mere strings to numerically ordered values through a process called "weather mapping." This was essential to make the dataset more interpretable for the model, ensuring a more accurate representation of the impact of weather conditions on wildfire behavior.

**Time Feature Engineering**

To make the raw date/time data understandable for the model, I employed time feature engineering, primarily focusing on calculating time intervals between key events. This involved creating new features in the dataset, such as 'time_to_discovery', 'time_to_report', 'time_to_dispatch', 'time_to_start_for_fire', 'time_to_assessment', 'time_to_ia_arrival', 'time_to_start_fighting', 'time_to_first_bucket_drop', and 'total_time_to_extinguish'. Each of these features was calculated by subtracting the 'fire_start_date' from other relevant timestamps, using a function compute_time_difference. For example, df['time_to_discovery'] was computed by finding the difference between the 'fire_start_date' and 'discovered_date'. This process was replicated for other critical timestamps, transforming them into more meaningful, model-friendly formats. After creating these new time interval features, I removed the original date columns to streamline the dataset, reducing its size for more efficient training and eliminating less informative data.

**Gaussian Mixture Model**

