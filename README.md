# ShasyaDrishti by Achinty Sharma

This project consists of a structured pipeline for data analysis and modeling, broken into three stages:

Stage 1: Exploratory Data Analysis (EDA)
Stage 2: Data Visualizations
Stage 3: Model Building & Evaluation

Each stage is represented by a Jupyter Notebook that contains relevant code and explanations.

#REQUIREMENTS

To run these notebooks, ensure you have the following dependencies installed:

	pip install numpy pandas matplotlib seaborn scikit-learn
	pip install notebook
	pip install xgboost lightgbm

After installing the dependencies, download the following datasets and rename as follows(Also make sure they are in the same directory of the jupyter notebooks):
		(Rename as aqi.csv)
	https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data
		(Rename as rainfall.csv)
	https://www.data.gov.in/catalog/rainfall-india
		(Rename as crops.csv)
	https://www.data.gov.in/catalog/district-wise-season-wise-crop-production-statistics-0
	
****************	FILE DESCRIPTIONS	****************

1.stage_1_EDA.ipynb

	PREPROCESSING
		a)Grouping months into crop seasons, Kharif, Rabi, Summer , Winter	
		b)Matching column names for consistency across datasets
		c)Modifying the AQI dataset, the Rainfall dataset, to match the structure of Crops Dataset
		d)Inconsistencies in the Rainfall dataset's State_Names, matching them with the Crops dataset's State_Names for merging.

	MERGING DATASETS
		a)Merging datasets on the basis of common columns, {State_Name , Crop_Year} in case of Rainfall + Crops and {State_Name , Crop_Year ,Season} in case of AQI + Crops
		b)FINAL DATASET CREATED, "final_merged.csv"

2.stage_2_Visualisations.ipynb

	EXPLORATORY VISUALISATIONS
		a)From the top of my head, whichever visualisations I thought would be useful, have been implemented here:
			1)Production By Year
			2)Box Plot of Production Distribution by Year
			3)Rolling Mean of Moving Average
			4)Top Crops based on Production
			5)Top States based on Production
			6)Season with highest Production
			7)Yield Plot(Production/Area) of top 10 crops by Production
			8)Parallel Coordinates Plot for Finding relationship between features
	
3.stage_3_Model.ipynb
	
	PREPROCESSING
		a)LabelEncoding the Categorical Columns

	VISUALISATIONS
		a)HEATMAP to find correlation between features and the target variable
		b)Scatter plot to visualize the predicted VS actual values
		c)SHAP Summary plot to find the most important feature
		d)Permutation Importance plot
	
	MODELS
		a)RandomForestRegressor
		b)GradientBoostingRegressor
		c)XGBRegressor
		d)LGBMRegressor

	EVALUATION METRIC
		R2_SCORE

****************	FINAL CONCLUSION	****************

In project ShasyaDrishti, I meticulously analyzed crop production data to uncover insights. Also successfully merged datasets of varying size and columns. Using various machine learning and Data Science techniques, I optimized the dataset and the model's hyperparameters to find the best model, XGBRegressor with an R2_SCORE of 0.916829647740307. Although the R2_Score is quite good, still the model can outperform.
	Further, I will move forward with integrating the Agricultural Market data and Soil, Temperature , weather data to create a full proof and robust model that will actually help farmers and government in allocating resources and move to sustainable farming.


