# Healthcare Insurance Datset
Our aim in this project is to use this dataset to understand features that impact health insurance charges. We will then use this information to build a model which can closely predict health insurance charges depending on the features identified, and stratify individuals into charge risk categories (low, moderate, high).

We will create a [Dashboard]() using Power BI that summarises the characteristics and correlations of the dataset, breaksdown how they affect charges, and how the model can be used as a tool to predict charges for potential customers.


# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## Dataset Content
This dataset contains information on the relationship between personal attributes (age, gender, BMI, family size, smoking habits), geographic factors, and their impact on medical insurance charges.
- The size is 55.63 kB
- There are 1338 rows and 7 columns
- The colums are: 
    - **age** - the insured person's age
    - **sex** - the sex (male/ female)
    - **bmi** - body mass index; a ratio of the height and weight used to estimate health
    - **chidren** - the number of children the insured has
    - **smoker** - whether they smoke (yes/ no)
    - **region** - what region of the USA they reside in
    - **charges** - the he medical insurance costs incurred by the insured person


## Business Requirements
We are a health insurance provider that wants to use this data to understand, model and predict healthcare charges so that we can provide competitive quotes to potential customers.

## Hypothesis and how to validate?
* We hypothesise that all given features could impact health insurance charges, but that **Age**, **BMI** and **Smoker** will have the biggest influences.
    - We will use a histogram to look at the distribution of numeric features to understand them better
    - We will use scatter plots to correlate **Age** and **BMI** with **Charges**.
    - We will us boxplots showing median **Charges** based on **Sex**, **Smoker**, **Children** and **Region**
    - We will integrate each of the categorical features into our **Age** vs **Charges** scatter plot
*

## Project Plan
- The data will be downloaded from [Kaggle](https://www.kaggle.com/datasets/willianoliveiragibin/healthcare-insurance/data), where it is hosted, and saved locally
- The data will be uploaded into a Jupyter Notebook, where ETL will be performed as detailed below
- A standard pipeline to explore, validate and clean the data was followed
- The choice to add encoded features as a new columns, rather than replacing the original, was taken because keeping the original headings helps create more  nderstandble plots 
- The output of ETL will be a cleaned and transformed DataFrame, ready for exploratory data analysis (EDA) 
* ETL:
    - Ensure valid ranges/ values for each feature
    - Check data types and output values are suitable
    - Check for missing data
    - Check for duplicated rows
    - Understand the unique values in categorical features 
    - Understand the spread, skewness and kurtosis in numerical features
    - Encode categorical features for further analysis/ processing
* EDA:
    - 
    - DataFrame with new column **BMI_Cat** saved as df_transformed_1.csv in new folder Dataset/Transformed  
* Data Model:
    - We built a model to predict health insurance costs for potential customers based on features found to impact **Charges** in the dataset 
    - New column **Obese** was added using BMI scores
    - It is a linear regression model based on **Age**, **Smoker** and **Obese**
    - DataFrame with new columns **Obese** and **Predicted_Cost** saved as df_model.csv in new folder Dataset/Model  

* How was the data managed throughout the collection, processing, analysis and interpretation steps?
* Why did you choose the research methodologies you used?

## The rationale to map the business requirements to the Data Visualisations
To understand what features impact **Charges** and make a model to estamate charges for potential customers:
- Each feature was visualised with respect to **Charges**
    - Continuous data using scatter plots
    - Categorical data using box plots
- Correlations were found with **Age**, **Smoker** and **BMI**
    - These features were visualised together with **Charges** to confirm impact
    - Feahtures were found to separate the data into 3 main groups
    - Correlation matrix used to visualise the features which correlate with **Charges**
    - Analysis to quantify features with most impact on **Charges** conducted
- Features used to make linear regression model
    - 3 scatter plots used, one for each group, to find the linear equation and R^2 which explains variation in **Charges** 
    - A scatter plot to show **Charges** vs. **Predicted_Cost** with R^2 used to assess how well the model explains the data

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 


## Main Data Analysis Libraries
* Here you should list the libraries you used in the project and provide an example(s) of how you used these libraries.
- Pandas: loading CSV file; cleaning and transforming the DataFrame
- Feature Engine: Ordinal Encoder
- Numpy: numpy.select to generate "Predicted_Costs" column
- Matplotlib: plot visualisations used for linear regression model
- Seaborn: scatter plots; box plots
- Plotly:


## Credits 

* In this section, you need to reference where you got your content, media and extra help from. It is common practice to use code from other repositories and tutorials, however, it is important to be very specific about these sources to avoid plagiarism. 
* You can break the credits section up into Content and Media, depending on what you have included in your project. 

* Dashboard - we'd like to credit the [dashboard](https://app.powerbi.com/groups/me/reports/97735ba6-f5c4-4b1c-a415-73a7d9d1dce1/324ed4c8b8ee7eaeb894?experience=power-bi) created by DaniDL346 in Healthcare_Insurance which was used for inspiration

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site



## Acknowledgements (optional)
* Thank the people who provided support through this project.