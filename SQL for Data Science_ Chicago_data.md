<center>
    <img src="https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/Logos/organization_logo/organization_logo.png" width="300" alt="cognitiveclass.ai logo"  />
</center>

<h1 align=center><font size = 5>Assignment: Notebook for Peer Assignment</font></h1>


# Introduction

Using this Python notebook you will:

1.  Understand three Chicago datasets
2.  Load the three datasets into three tables in a Db2 database
3.  Execute SQL queries to answer assignment questions


## Understand the datasets

To complete the assignment problems in this notebook you will be using three datasets that are available on the city of Chicago's Data Portal:

1.  <a href="https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01">Socioeconomic Indicators in Chicago</a>
2.  <a href="https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01">Chicago Public Schools</a>
3.  <a href="https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01">Chicago Crime Data</a>

### 1. Socioeconomic Indicators in Chicago

This dataset contains a selection of six socioeconomic indicators of public health significance and a “hardship index,” for each Chicago community area, for the years 2008 – 2012.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01&cm_mmc=Email_Newsletter-\_-Developer_Ed%2BTech-\_-WW_WW-\_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

### 2. Chicago Public Schools

This dataset shows all school level performance data used to create CPS School Report Cards for the 2011-2012 school year. This dataset is provided by the city of Chicago's Data Portal.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01&cm_mmc=Email_Newsletter-\_-Developer_Ed%2BTech-\_-WW_WW-\_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)

### 3. Chicago Crime Data

This dataset reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2001 to present, minus the most recent seven days.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01&cm_mmc=Email_Newsletter-\_-Developer_Ed%2BTech-\_-WW_WW-\_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ)


### Download the datasets

This assignment requires you to have these three tables populated with a subset of the whole datasets.

In many cases the dataset to be analyzed is available as a .CSV (comma separated values) file, perhaps on the internet. Click on the links below to download and save the datasets (.CSV files):

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCensusData.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Census Data</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoPublicSchools.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Public Schools</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCrimeData.csv?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Crime Data</a>

**NOTE**: For the learners who are encountering issues with loading from .csv in DB2 on Firefox, you can download the .txt files and load the data with those:

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCensusData.txt?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Census Data</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoPublicSchools.txt?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Public Schools</a>

*   <a href="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/data/ChicagoCrimeData.txt?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01" target="_blank">Chicago Crime Data</a>

**NOTE:** Ensure you have downloaded the datasets using the links above instead of directly from the Chicago Data Portal. The versions linked here are subsets of the original datasets and have some of the column names modified to be more database friendly which will make it easier to complete this assignment.


### Store the datasets in database tables

To analyze the data using SQL, it first needs to be stored in the database.

While it is easier to read the dataset into a Pandas dataframe and then PERSIST it into the database as we saw in Week 3 Lab 3, it results in mapping to default datatypes which may not be optimal for SQL querying. For example a long textual field may map to a CLOB instead of a VARCHAR.

Therefore, **it is highly recommended to manually load the table using the database console LOAD tool, as indicated in Week 2 Lab 1 Part II**. The only difference with that lab is that in Step 5 of the instructions you will need to click on create "(+) New Table" and specify the name of the table you want to create and then click "Next".

<img src = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/images/LoadingData.png">

##### Now open the Db2 console, open the LOAD tool, Select / Drag the .CSV file for the first dataset, Next create a New Table, and then follow the steps on-screen instructions to load the data. Name the new tables as follows:

1.  **CENSUS_DATA**
2.  **CHICAGO_PUBLIC_SCHOOLS**
3.  **CHICAGO_CRIME_DATA**


### Connect to the database

Let us first load the SQL extension and establish a connection with the database

The following required modules are pre-installed in the Skills Network Labs environment. However if you run this notebook commands in a different Jupyter environment (e.g. Watson Studio or Ananconda) you may need to install these libraries by removing the `#` sign before `!pip` in the code cell below.



```python
# These libraries are pre-installed in SN Labs. If running in another environment please uncomment lines below to install them:
# !pip install --force-reinstall ibm_db==3.1.0 ibm_db_sa==0.3.3
# Ensure we don't load_ext with sqlalchemy>=1.4 (incompadible)
# !pip uninstall sqlalchemy==1.4 -y && pip install sqlalchemy==1.3.24
# !pip install ipython-sql
```


```python
%load_ext sql
```

In the next cell enter your db2 connection string. Recall you created Service Credentials for your Db2 instance in first lab in Week 3. From your Db2 service credentials copy everything after db2:// (except the double quote at the end) and paste it in the cell below after ibm_db_sa://

<img src ="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork/labs/FinalModule_Coursera_V5/images/details.png">



```python
# Remember the connection string is of the format:
# %sql ibm_db_sa://my-username:my-password@my-hostname:my-port/my-db-name?security=SSL
# Enter the connection string for your Db2 on Cloud database instance below
%sql ibm_db_sa://mnf86716:RjHV727maVKLqFgb@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB?security=SSl
```




    'Connected: mnf86716@BLUDB'



## Problems

Now write and execute SQL queries to solve assignment problems

### Problem 1

##### Find the total number of crimes recorded in the CRIME table.



```python
%sql select count(*) from CRIME_DATA
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>533</td>
        </tr>
    </tbody>
</table>



### Problem 2

##### List community areas with per capita income less than 11000.



```python
%sql select COMMUNITY_AREA_NAME from CENSUS_DATA where PER_CAPITA_INCOME <11000
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>community_area_name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>West Garfield Park</td>
        </tr>
        <tr>
            <td>South Lawndale</td>
        </tr>
        <tr>
            <td>Fuller Park</td>
        </tr>
        <tr>
            <td>Riverdale</td>
        </tr>
    </tbody>
</table>



### Problem 3

##### List all case numbers for crimes  involving minors?(children are not considered minors for the purposes of crime analysis)



```python
%sql select CASE_NUMBER from CRIME_DATA where DESCRIPTION LIKE '%MINOR%'
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>case_number</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>HL266884</td>
        </tr>
        <tr>
            <td>HK238408</td>
        </tr>
    </tbody>
</table>



### Problem 4

##### List all kidnapping crimes involving a child?



```sql
%%sql SELECT DISTINCT CASE_NUMBER, PRIMARY_TYPE, DESCRIPTION FROM CRIME_DATA 
WHERE PRIMARY_TYPE = 'KIDNAPPING'
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>case_number</th>
            <th>primary_type</th>
            <th>description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>HN144152</td>
            <td>KIDNAPPING</td>
            <td>CHILD ABDUCTION/STRANGER</td>
        </tr>
    </tbody>
</table>



### Problem 5

##### What kinds of crimes were recorded at schools?



```sql
%%sql
select DISTINCT PRIMARY_TYPE FROM CRIME_DATA WHERE LOCATION_DESCRIPTION LIKE '%SCHOOL%'
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>primary_type</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>ASSAULT</td>
        </tr>
        <tr>
            <td>BATTERY</td>
        </tr>
        <tr>
            <td>CRIMINAL DAMAGE</td>
        </tr>
        <tr>
            <td>CRIMINAL TRESPA</td>
        </tr>
        <tr>
            <td>NARCOTICS</td>
        </tr>
        <tr>
            <td>PUBLIC PEACE VI</td>
        </tr>
    </tbody>
</table>



### Problem 6

##### List the average safety score for each type of school.



```sql
%%sql
SELECT "Elementary, Middle, or High School", AVG(SAFETY_SCORE) as Average_safety_score FROM PUBLIC_SCHOOL
GROUP BY "Elementary, Middle, or High School"
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>Elementary, Middle, or High School</th>
            <th>average_safety_score</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>ES</td>
            <td>49</td>
        </tr>
        <tr>
            <td>HS</td>
            <td>49</td>
        </tr>
        <tr>
            <td>MS</td>
            <td>48</td>
        </tr>
    </tbody>
</table>



### Problem 7

##### List 5 community areas with highest % of households below poverty line



```sql
%%sql
select COMMUNITY_AREA_NAME, PERCENT_HOUSEHOLDS_BELOW_POVERTY FROM CENSUS_DATA ORDER BY PERCENT_HOUSEHOLDS_BELOW_POVERTY DESC FETCH FIRST 5 ROWS ONLY
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>community_area_name</th>
            <th>percent_households_below_poverty</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Riverdale</td>
            <td>56.5</td>
        </tr>
        <tr>
            <td>Fuller Park</td>
            <td>51.2</td>
        </tr>
        <tr>
            <td>Englewood</td>
            <td>46.6</td>
        </tr>
        <tr>
            <td>North Lawndale</td>
            <td>43.1</td>
        </tr>
        <tr>
            <td>East Garfield Park</td>
            <td>42.4</td>
        </tr>
    </tbody>
</table>



### Problem 8

##### Which community area is most crime prone?



```sql
%%sql
select COMMUNITY_AREA_NUMBER, COUNT(COMMUNITY_AREA_NUMBER) AS FREQUENCY FROM CRIME_DATA
GROUP BY COMMUNITY_AREA_NUMBER
ORDER BY COUNT(COMMUNITY_AREA_NUMBER) DESC
FETCH FIRST 1 ROWS ONLY
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>community_area_number</th>
            <th>frequency</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>25</td>
            <td>43</td>
        </tr>
    </tbody>
</table>



Double-click **here** for a hint

<!--
Query for the 'community area number' that is most crime prone.
-->


### Problem 9

##### Use a sub-query to find the name of the community area with highest hardship index



```sql
%%sql
select COMMUNITY_AREA_NAME, HARDSHIP_INDEX FROM CENSUS_DATA WHERE HARDSHIP_INDEX IN (SELECT MAX(HARDSHIP_INDEX) FROM CENSUS_DATA)
```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>community_area_name</th>
            <th>hardship_index</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Riverdale</td>
            <td>98</td>
        </tr>
    </tbody>
</table>



### Problem 10

##### Use a sub-query to determine the Community Area Name with most number of crimes?



```sql
%%sql
select COMMUNITY_AREA_NAME FROM CENSUS_DATA WHERE COMMUNITY_AREA_NUMBER IN
(select COMMUNITY_AREA_NUMBER FROM CRIME_DATA
GROUP BY COMMUNITY_AREA_NUMBER
ORDER BY COUNT(COMMUNITY_AREA_NUMBER) DESC
FETCH FIRST 1 ROWS ONLY)

```

     * ibm_db_sa://mnf86716:***@55fbc997-9266-4331-afd3-888b05e734c0.bs2io90l08kqb1od8lcg.databases.appdomain.cloud:31929/BLUDB
    Done.





<table>
    <thead>
        <tr>
            <th>community_area_name</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Austin</td>
        </tr>
    </tbody>
</table>



Copyright © 2020 [cognitiveclass.ai](cognitiveclass.ai?utm_source=bducopyrightlink&utm_medium=dswb&utm_campaign=bdu). This notebook and its source code are released under the terms of the [MIT License](https://bigdatauniversity.com/mit-license?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDB0201ENSkillsNetwork20127838-2022-01-01&cm_mmc=Email_Newsletter-\_-Developer_Ed%2BTech-\_-WW_WW-\_-SkillsNetwork-Courses-IBMDeveloperSkillsNetwork-DB0201EN-SkillsNetwork-20127838&cm_mmca1=000026UJ&cm_mmca2=10006555&cm_mmca3=M12345678&cvosrc=email.Newsletter.M12345678&cvo_campaign=000026UJ).


## Author(s)

<h4> Hima Vasudevan </h4>
<h4> Rav Ahuja </h4>
<h4> Ramesh Sannreddy </h4>

## Contribtuor(s)

<h4> Malika Singla </h4>

## Change log

| Date       | Version | Changed by        | Change Description                             |
| ---------- | ------- | ----------------- | ---------------------------------------------- |
| 2021-11-17 | 2.6     | Lakshmi           | Updated library                                |
| 2021-05-19 | 2.4     | Lakshmi Holla     | Updated the question                           |
| 2021-04-30 | 2.3     | Malika Singla     | Updated the libraries                          |
| 2021-01-15 | 2.2     | Rav Ahuja         | Removed problem 11 and fixed changelog         |
| 2020-11-25 | 2.1     | Ramesh Sannareddy | Updated the problem statements, and datasets   |
| 2020-09-05 | 2.0     | Malika Singla     | Moved lab to course repo in GitLab             |
| 2018-07-18 | 1.0     | Rav Ahuja         | Several updates including loading instructions |
| 2018-05-04 | 0.1     | Hima Vasudevan    | Created initial version                        |

## <h3 align="center"> © IBM Corporation 2020. All rights reserved. <h3/>

