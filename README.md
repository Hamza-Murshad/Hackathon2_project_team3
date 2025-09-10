# Healthcare Insurance Dataset
Our aim in this project is to use this dataset to understand features that impact health insurance charges. We will then use this information to build a model which can closely predict health insurance charges depending on the features identified, and stratify individuals into charge risk categories (low, moderate, high).

We will create a [Dashboard]() using Power BI that summarises the characteristics and correlations of the dataset, breaks down how they affect charges, and how the model can be used as a tool to predict charges for potential customers.


# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Dataset Content
This [dataset](https://www.kaggle.com/datasets/willianoliveiragibin/healthcare-insurance) contains information on the relationship between personal attributes (age, gender, BMI, family size, smoking habits), geographic factors, and their impact on medical insurance charges.
- The size is 55.63 kB
- There are 1338 rows and 7 columns
- The columns are: 
    - **age** - the insured person's age
    - **sex** - the sex (male/ female)
    - **bmi** - body mass index; a ratio of the height and weight used to estimate health
    - **children** - the number of children the insured has
    - **smoker** - whether they smoke (yes/ no)
    - **region** - what region of the USA they reside in
    - **charges** - the medical insurance costs incurred by the insured person


## Business Requirements
We are a health insurance provider that wants to use this data to understand, model and predict healthcare charges so that we can provide competitive quotes to potential customers.

## Hypothesis and how to validate?
* We hypothesise that all given features could impact health insurance charges, but that **Age**, **BMI** and **Smoker** will have the biggest influences.
    - We will use a histogram to look at the distribution of numeric features to understand them better
    - We will use scatter plots to correlate **Age** and **BMI** with **Charges**.
    - We will use boxplots showing median **Charges** based on **Sex**, **Smoker**, **Children** and **Region**
    - We will integrate each of the categorical features into our **Age** vs **Charges** scatter plot
*

## Project Plan
- The data will be downloaded from [Kaggle](https://www.kaggle.com/datasets/willianoliveiragibin/healthcare-insurance/data), where it is hosted, and saved locally
- The data will be uploaded into a Jupyter Notebook, where ETL will be performed as detailed below
- A standard pipeline to explore, validate and clean the data was followed
- The choice to add encoded features as a new columns, rather than replacing the original, was taken because keeping the original headings helps create more understandable plots 
- The output of ETL will be a cleaned and transformed DataFrame, ready for exploratory data analysis (EDA) 
* **ETL:**
    - Ensured valid ranges/ values for each feature
    - Checked data types and output values are suitable
    - Checked for missing data
    - Checked for duplicated rows
    - Understood the unique values in categorical features 
    - Understood the spread, skewness and kurtosis in numerical features
    - Encoded categorical features for further analysis/ processing
* **EDA:**
    - Loaded and explored the cleaned insurance dataset
    - Visualised distributions of different variables: **Charges**, **Age**, **BMI**, and **Children**
    - Investigated relationships between Charges and other factors such as **Smoker/Non-Smoker**, **BMI**, **Age**, **Region**, and **Children**.
    - Categorised **BMI** into 4 unique classes `(Underweight, Normal, Overweight, Obese)` and compared charges across these categories  
    - Used various plots like histograms, box plots, scatter plots and heatmaps to identify trends and correlations. 
    - Provided interpretations for outliers and category impacts to support further analysis. 
    - DataFrame with new column **BMI_Cat** saved as df_transformed_1.csv in new folder Dataset/Transformed  
* **Data Model:**
    - We built a model to predict health insurance costs for potential customers based on features found to impact **Charges** in the dataset 
    - New column **Obese** was added using BMI scores
    - It is a linear regression model based on **Age**, **Smoker** and **Obese**
    - DataFrame with new columns **Obese** and **Predicted_Cost** saved as df_model.csv in new folder Dataset/Model  
* **Data Visualisations:**
    - Created clear and informative visualisations to highight key patterns in the dataset
    - Explored the impact of **Smoker/Non-Smoker**, **BMI**, **Age**, **Sex** and **Region** on Charges using various plots
    - Used side by side, box, violin, scatter and 3d plots to find trends
    - Investigated further relationships between each factor rather than just against charges to reveal patterns
    - Summarised findings with group statistics to support visual insights

* **Why we chose the methodologies we used:**
    - We selected chose these methodologies to produce a thorough analysis of the insurance dataset. In **ETL** we used processes which guaranteed data quality (through cleaning) and consistency for further analysis in out other notebooks. **EDA** allowed us to understand the structure, distributions and relationships within the dataset which guided our focus towards the most influential factors. For **Data Visualisation** we used a variety of plots to clearly show the constant trends through the dataset for both technical and non-technical audiences. This multi-step approach ensured that our findings were evaluated seamlessly and were actionable for business decision-making. 

## The rationale to map the business requirements to the Data Visualisations
To understand what features impact **Charges** and make a model to estimate charges for potential customers:
- Each feature was visualised with respect to **Charges**
    - Continuous data using scatter plots
    - Categorical data using box plots
- Correlations were found with **Age**, **Smoker** and **BMI**
    - These features were visualised together with **Charges** to confirm impact
    - Features were found to separate the data into 3 main groups
    - Correlation matrix used to visualise the features which correlate with **Charges**
    - Analysis to quantify features with most impact on **Charges** conducted
    - We highlighted the importance of visualising both individual and combined effects of the features
- Features used to make linear regression model
    - 3 scatter plots used, one for each group, to find the linear equation and R^2 which explains variation in **Charges** 
    - A scatter plot to show **Charges** vs. **Predicted_Cost** with R^2 used to assess how well the model explains the data

## Analysis techniques used
* **Analysis Methods used:**
    - Used descriptive statistics
    - Data cleaning techniques to handle missing values, duplicates and inconsistent data
    - Encoding of categorical variables for analysis and visualisation
    - EDA using visualisations to find trends and correlations. 
    - Correlations analysis to find trends between each variable
    - Linear regression modelling to predict charges 
* **Limitations:**
    - Dataset was relatively small (only 1338 rows)
    - Limited set of features recorded in dataset 
    - Having access to other factors could improve model accuracy

* **How we structured the data analysis:**
    - It was structured in a logical sequence: ETL for data quality, EDA and data visualisations to explore and find patterns and modelling to predict further data. 

* **How we used generative tools to help:**
    - We used generative tools such as co-pilot and ChatGPT to help create a model for predicting charges
    - Co-pilot was used to assess feature importance through linear regression coefficients and also measure the impact features had

## Dashboard Design
* **Dashboard Pages and Content:**
    - The dashboard has 3 pages: `Main Summary, Breakdown by Attribute, Prediction Model`
    - In the `Main Summary` page we have as follows:
        - Cards displaying important and valuable information. 
        - 3 unique donut charts that show the **Sex**, **Region** and **Children**
        - Interactive slicers and dropdowns for the features allowing the various plots on the dashboard to change live 
        - Scatter plot showing average of **BMI** by **Smoker**, **Age** and **Charges**
        - Another scatter plot showing **Smoker**, **BMI** and **Charges**
    - In the `Breakdown by Attribute` page we have as follows:
        - A column chart showing **Median Charges** by **Smoker**
        - A stacked column chart showing **Median Charges** by **Age**
        - A column chart showing **Median Charges** by **Obesity**
        - A stacked column chart Showing **Median Charges** by **BMI**
        - A stacked column chart showing **Median Charges** by **Region**
        - A stacked column chart showing **Median Charges** by **Children**
        - Interactive slicers and dropdown menus for the features allowing the various plots on the dashboard to change live 
    - In the `Prediction Model` page we have as follows:
        - Cards showing important data
        - Scatter chart of **Charges** by **Age** for Non-Smokers
        - Scatter chart of **Charges** by **Age** for Non-Obese 
        - Scatter chart of **Charges** by **Age** for Smokers and Obese
        - Interactive slicers and dropdown menus of the features allowing the various plots on the dashboard to change live 

    - Data insights were communicated using clear and intuitive visualisations and concise summaries. For technical audiences, an option to interact with the data was available through sliders and dropdown menus. The dashboard used interactive charts, color coding and simple metrics to highlight key findings and trends. 


## Development Roadmap
* **Challenges Faced and Strategies:**
    - Faced limited dataset size and features which restricted better accuracy. We addressed this by focusing on robust EDA and also clearly communicating and keeping in mind the limitations when finding trends
    - We encountered data quality issues such as duplicated data and inconsistent values which we resolved in the ETL


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.
- Pandas: loading CSV file; cleaning and transforming the DataFrame
    - Example: `df = pd.read_csv("Dataset/Raw/insurance.csv")`
- Feature Engine: Ordinal Encoder
    - Example: `imputer = CategoricalImputer(imputation_method='frequent')`
- Numpy: numpy.select to generate "Predicted_Costs" column
    - Example: `df["charges"] = np.round(df["charges"], 2)`
- Matplotlib: plot visualisations used for linear regression model
    - Example: `plt.figure(figsize=(10,6)); plt.hist(df["charges"])`
- Seaborn: scatter plots; box plots
    - Example: `sns.boxplot(x="Smoker", y="Charges", data=df)`
- Plotly: Used for interactive and 3D visualisations
    - Example: `fig = px.scatter(df, x="Age", y="Charges", color="Sex")`
- Scikit-learn: Used for building and evaluating an ML model
    - Example: `kmeans = KMeans(n_clusters=3, random_state=42)`
`df['cluster'] = kmeans.fit_predict(df[['Age', 'BMI', 'Charges']])`


## Credits 

* Dashboard - we'd like to credit the [dashboard](https://app.powerbi.com/groups/me/reports/97735ba6-f5c4-4b1c-a415-73a7d9d1dce1/324ed4c8b8ee7eaeb894?experience=power-bi) created by DaniDL346 in Healthcare_Insurance which was used for inspiration

* Copilot and ChatGPT - Helped create the predictive model

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)



## Acknowledgements (optional)
* Thank the people who provided support through this project.