# Analysis of 1999-2008 Hospital Operations in the United States

### _What’s the average number of days a patient stays in the hospital?_
---


#### Introduction
In this project, I chose to practice SQL querying from multiple sources to provide analysis of hospital care and patient information. When it concerns patient care, there is a fine line between balancing business productivity and customer service. As a professional who has construction experience helping to remodel hospital rooms, I’ve wondered how hospitals forecast the number of different diseases and people they can help each year let alone people each month. Oftentimes it takes between 6 to 36 months (sometimes 5 years) to take an Owner’s requirements and budget through pre-planning, design, budgeting, and more planning through construction. Taking this knowledge into perspective can help understand why managing patient turnover in hospital beds would be an important part of business operations.  

#### Objective
I've been asked to provide various lists using patient statistics.

##### Here are a few questions I set out to answer:

1. What does the distribution of time a patient spends in the hospital look like? Do the majority of patients stay less than 7 days?
2. What are the 5 most common medical specialties? 
3. Which medical specialties have the highest number of procedures?
4. Does the number of lab procedures a patient receives affect the number of days a patient stays in the hospital?
5. Does patient demographics like race influence the number of lab procedures needed?


##### Key Insights

1. The average number of days a patient spends in the hospital is 4.4 days, and 85% of patients spend less than 7 days in the hospital.
2. There are 73 different medical specialties with the 5 most common medical specialties associated with unknown, internal medicine, emergency/trauma, family practice/ general medicine, and cardiology.
3. Surgery-thoracic, Surgery-Cardiovascular/Thoracic, Radiologist, Cardiology, and Surgery-Vascular as the 5 medical specialties with the highest average number of procedures. 
4. The more lab procedures a patient has the longer a patient stays in the hospital or vice-versa.
5. Among the 6 identified racial categories, the average number of lab procedures is within a small margin of one another, from 40.9 to 44.1.

#### The Data
The hospital information contained in this dataset was taken from the [University of California Machine Learning Repository](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008). This dataset represents ten years (1999-2008) of clinical care at 130 US hospitals and integrated delivery networks. Each row is a hospital record for a patient diagnosed with diabetes who underwent laboratory work, was given medications, and stayed at the hospital from 1 to 14 days.

The dataset can also be found on [Kaggle](https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/notebook#Data-Preparation-&-Exploration). It contains 101,766 rows (101,765 as patients) and 52 attributes divided into 2 separate tables. 
An extensive data dictionary can be found here. Only the following 8 attributes were used in this analysis:

* patient_nbr 
* admission_type_id 
* time_in_hospital
* medical_specialty
* num_lab_procedures
* num_procedures
* num_medications
* race

#### The Analysis + Commentary
_What does the distribution of time a patient spends in the hospital look like? Do the majority of patients stay less than 7 days?_

<img src="images/SQL Healthcare 01.png">

I used the following queries to answer the question above. The results showed 4.4 days as the average time a patient spends in the hospital and further analysis showed 85% of patients stayed in the hospital for less than 7 days. SQL is typically not the best way to show visualizations, but by using the RPAD function and division, this query can be depicted showing patients represented as “stars” or asterisks in the histogram plotted below.  

<img src="images/SQL Healthcare histogram.png">
---

_What are the 5 most common medical specialties?_

<img src="images/SQL Healthcare 02.png"/>
<img src="images/SQL Healthcare 02 Results.png"/>

For this question, I used queries focused on finding the number of unique medical specialties the hospital performed and the specialties performed the most within the 130 hospitals and integrated delivery networks. Results showed there are 73 different medical specialties with the 5 most common medical specialties associated with unknown, internal medicine, emergency/trauma, family practice/ general medicine, and cardiology.

_Which medical specialties have the highest number of procedures?_

<img src="images/SQL Healthcare avg prod.png"/>

Because the queries used in question 2 focused on the number of medical specialties overall, I dived deeper into these initial queries to find the average number of procedures performed under the 5 most common medical specialties. The following query resulted in Proctology showing the medical specialty with the highest average number of procedures however the count showed 1, which may indicate an outlier. To account for outliers within the dataset, I did further analysis using the Having function. 

<img src="images/SQL Healthcare avg prod 04.png"/>

---

<img src="images/SQL Healthcare avg having.png"/>

The Having function was used to filter for the medical specialty that had more than 50 patients and an average procedure of 2.5 or more. Now the results show Surgery-Thoracic, Surgery-Cardiovascular/Thoracic, Radiologist, Cardiology and Surgery-Vascular as the 5 medical specialties with the highest average number of procedures. 

<img src="images/SQL Healthcare avg med spec 04.png"/>

_Does the number of procedures a patient receives affect the number of days a patient stays in the hospital?_

<img src="images/SQL Healthcare 05 Results.png"/>

To find the answer, I broke this question into two parts. I found the average number of days a patient stayed in the hospital and the number of lab procedures a patient had. Then I separated the averages into 3 bins ranging from few; to average and then many using the case when command to separate the averages. The following results show a correlation between the number of lab procedures and the number of days a patient stays in the hospital. The longer a patient stays in the hospital the more lab procedures they have, or vice-versa.

<img src="images/SQL Healthcare avg patient.png"/>

To answer the following question, I used the JOIN command to combine two tables together. The patient’s health information was provided in one table while the patient’s demographics were in another. Then I used the patient number, race, and the number of lab procedure attributes to find the average number of lab procedures for the total number of patients grouped by race. 

<img src="images/SQL Healthcare Race query.png"/>

_Does patient demographics like race influence the number of lab procedures needed?_

<img src="images/SQL Healthcare Race qresults.png"/>

The results indicate that, among the six identified racial categories, the average number of lab procedures is closely clustered, ranging from 40.9 to 44.1.

#### Insights and Recommendations
I enjoyed exploring hospital operations and patient healthcare information to practice SQL queries.  If you enjoyed reading my analysis and are interested in knowing more, please feel free to connect with me on LinkedIn and check out my other projects!
