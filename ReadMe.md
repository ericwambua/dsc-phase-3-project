# TANZANIA WATER WELL ANALYSIS

![image.png](attachment:image.png)

### Project Overview
Tanzania, a developing country with a population of over 67 million(according to https://www.worldometers.info/world-population/tanzania-population/), faces significant challenges in providing clean water to its citizens. Many existing water wells are either in need of repair or have become non-functional hence many families have a challenge accessing this basic need. This project aims to address this issue by developing a predictive model to classify the condition of water wells.

### Project Objective:
The primary objective of this project is to build a classifier that can predict the condition of water wells based on relevant data such as the type of pump, installation date, and other pertinent factors. The classifier will be designed with the primary aim of aiding:

a. NGOs: Assist non-governmental organizations (NGOs) in identifying wells that require repair or maintenance, enabling them to allocate their resources efficiently and ensure a sustainable supply of clean water.

b. Government of Tanzania: Provide insights into the patterns and factors contributing to non-functional wells, enabling evidence-based decision-making for the construction of new wells. This may involve converting the ternary classification problem into a binary one for simplicity.

### Methodology:
The project will employ a data-driven approach, using historical well data, to train and test a machine learning classifier. The methodology will involve data preprocessing, feature engineering, model selection, and evaluation. Additionally, geospatial analysis may be used to incorporate the geographical aspect of well locations.

### The Data
 
 I utilized data downloaded from Drive Data (https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/data/) which consisted of:
- Training set labels	:The dependent variable (status_group) for each of the rows in Training set values
- Training set values	:The independent variables for the training set

I merged the two datasets which resulted 59400 rows and the  following columns;

- 1.date_recorded	            -The date the row was entered
- 2	funder	                    -Who funded the well
- 3	gps_height	                -Altitude of the well
- 4	installer	                -Organization that installed the well
- 5	longitude	                -GPS coordinate
- 6	latitude	                -GPS coordinate
- 7	wpt_name	                -Name of the waterpoint if there is one
- 8	num_private	                -Number of private waterpoints
- 9	basin	                    -Geographic water basin
- 10	subvillage	            -Geographic location
- 11	region	                -Geographic location
- 12	region_code	            -Geographic location
- 13	district_code        	-Geographic location
- 14	lga	                    -Geographic location
- 15	ward	                -Geographic location
- 16	population	            -Population utilizing the well
- 17	public_meeting	        -True/False
- 18	recorded_by	            -Group entering this row of data
- 19	scheme_management	    -Management of the waterpoint
- 20	scheme_name	            -Management of the waterpoint
- 21	permit	                -If the waterpoint is permitted
- 22	construction_year	    -Year the waterpoint was constructed
- 23	extraction_type	        -The kind of extraction the waterpoint uses
- 24	extraction_type_group	-The kind of extraction the waterpoint uses
- 25	extraction_type_class	-The kind of extraction the waterpoint uses
- 26	management	            -How the waterpoint is managed
- 27	management_group    	-How the waterpoint is managed
- 28	payment	                -What the water costs
- 29	payment_type	        -How the water is paid
- 30	water_quality	        -The quality of the water
- 31	quality_group	        -The quality of the water
- 32	quantity	            -The quantity of water
- 33	quantity_group      	-The quantity of water
- 34	source	                -The source of the water
- 35	source_type	            -The source of the water
- 36	source_class	        -The source of the water
- 37	waterpoint_type     	-The kind of waterpoint
- 38	waterpoint_type_group	-The kind of waterpoint
- 39.   status_group	        -Condition of the well

### Exploratory data analysis (EDA)

1. The Dependent Variable made of the status_group . The column has three categores of functional wells with a population of 32,259 , non-functional wells with 22824 wells and those that are functional but need repairs which were 4,317 in numbers. Being my dependent category, I decided to merge the non-functional wells and the wells that were functional but needed repairs into one category of needs repair. This was helpful when designing a prediction model and was helpful to the stakeholders too as it will help them identify the wells that need repairs. This gave a 54.3% of functional well and 45.7% of need repair category. The margin is 8.6% and I felt the class was well balanced and hence no need for generating synthetic samples
![image-2.png](attachment:image-2.png)


2. Well Location and Functionality. The wells seem to be evenly distributed across Tanzania. The region of around -11 lattitude and around 39 longitudes has the majority number of non- functional wells. Majority of the overall wells are situated on the upper half of the map
![image-3.png](attachment:image-3.png)

3. Water Basin . The lake Victoria basin has the largest number of wells with a figure of 10,248 followed by Pangani and Rufiji which had 8940 and 7976 wells respectively. Lake Lukwa basin had the least number with 2454 wells.
![image-5.png](attachment:image-5.png)

4. Water Quality. The soft water wells have the largest number of functioning wells and their ratio is significantly larger compared to those that need repair in the same category. The salty wells and those whose water quality is unknown have their non-functional number of pumps being more than those that are functional.
![image-6.png](attachment:image-6.png)

5. Year of Construction. Majority of the wells had no clear year of constuction(20,709 wells),followed by those constructed between 2000 to 2009 with a figure of 15,330 wells. The least number of wells ,538, were constructed between the year 1960 and 1969. There was a noticed trend of increase in number of wells by decades untill between the years 2010 to 2019 where a significant drop in number of wells constructed was observed
![image-7.png](attachment:image-7.png)

6. Management Group. Wells managed by user-groups had the largest number of 52490,followed by commercial and parastatals. There was a entries of Unknown and other ,which had the lowest number of 561 and 943 respectively
![image-8.png](attachment:image-8.png)

7. Water Payment. Majority of the wells are free (25348). The wells whereby water is paid per bucket drawn and those paid monthly compose a big number of 8985 and 8300 respectively. The wells that the users pay annually and those with other payment modes compose the least population on 3642 and 1054 respectively. Wells where people pay to draw water seem to be better managed and have the largest number of functional wells compared to the wells that need repair.

8. Waterpoint Type: The communal standpipe category has the largest number. In this category, we have wells that have only one stand pipe(28,522 of them) and those that have multiple standpipes(6103 in number). Cattle trough and dams have the lowest number of 116 and 7 wells respectively. In the categories of communal standpipe,hand pump, improved spring and cattle trough the number of functional wells outnumber those of non-functional and those that need repair. In the category of communal stand pipe multiple and other the non-funtional wells were observed to have larger numbers than the functional wells.
![image-9.png](attachment:image-9.png)


### Recommendation
- Prioritize Soft Water Wells
- Implement Payment Plans
- Utilize User Group Management
- Ensure Sufficient Water Quantity
- Invest in Ground Water and Communal Stand Pipes
- Utilize the RandomForestClassifier Model

### Conclusion
- Prioritizing the construction of wells with soft water
- Introducing payment plans, no matter how modest
- Entrusting well management to user groups has shown a consistent positive impact on functionality
- Constructing wells that guarantee a sufficient water supply is vital.
- Prioritizing the construction and maintenance of groundwater and Communal Stand Pipe wells is a strategic investment
- The RandomForestClassifier model, with an 80% accuracy rate after tuning, proves to be a valuable tool for assessing well conditions



```python

```
# dsc-phase-3-project
