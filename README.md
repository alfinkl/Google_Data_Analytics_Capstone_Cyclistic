# Google_Data_Analytics_Capstone_Cyclistic
A case study by Google as the last project as requirement for the Google Data Analyst Certificate
## Introduction
In this case study created by Google Analytics, with the scenario the learner is working at a fictional company, Cyclistic. The goal for the case study is to help learners to have an analysis simulation with a lot of data which follows the steps of the analysis process: Ask, Prepare, Process, Analyze, Share, and Act.
## Background
Cyclistic is a bike share company in Chicago, with 5,800 bicycles and 600 docking stations. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, learner wants to understand how casual riders and member riders use Cyclistic bikes differently. From these insights, learner will help design the marketing strategy to convert casual riders into member riders.
## Objective
Recommend the marketing strategy to convert casual riders into annual member riders.
Three questions will guide the future marketing program:
How do annual members and casual riders use Cyclistic bikes differently?
Why would casual riders buy Cyclistic annual memberships?
How can Cyclistic use digital media to influence casual riders to become members?
The marketing director has assigned the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?
## Data Integrity
The data of Cyclistic’s historical trip could be downloaded from divvy_tripdata. This analysis is conducted using the range of data from January 2025 to December 2025, with this data is under this license by Motive International Inc.
According to the data-privacy issue, the database does not include any personal information, such as credit card numbers that could determine any customer’s personal information.

## Process
### Tools
This analysis use PostgreSQL for process the data, such as cleaning data, and manipulate the data, since the size of June to December data is too large for Google Sheets with approximately more than 100 MB for each files, so I decide to use all the process on PostgreSQL from the beginning. Combine with Tableau software to visualize my data through charts, graphs, and maps.
Before the add table process to PostgreSQL, the first step is to identify the character of each column. The figure below showed the add table process on PostgreSQL :

![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/fe20bbd684c558b7ac390338349e7692219af333/Add%20table%20process.png)

### Cleaning Data
After adding twelve months of datasets, the cleaning process starts with querying the number of the Null data. The figure below is the results of the query : 
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/db590e5b9fc36dd95af8ac01e7860c28e8634789/Null%20Data%20results.png)

The next step is to eliminate the duplicate data, using command _ctid_ with ride_id as the pivot for this process to eliminate duplicate ride_id appearing on the datasets. Using this technique to let the command choose only the first unique column and erase the copy of the same column. Figure below is the query process for deleting the duplicate data : 
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/cd72184ec7ebec709b8b5ce63e2e2a3cc96507c7/Cleaning%20Duplicate%20Data.png)

## Analyze and Findings
First of all, this analysis is using a seasonal approach to classify the monthly-data. The seasonal time in the US, divided by 4 seasons, is winter start from December to February, spring start from March to May, summer season from June to August, and fall or known as autumn start from September to November.
With the classification of the seasonal time, I count the total ride count for member and casual together for each season. 
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/bc8b63e074c8a508463c83d197c7f963df568b44/Total%20Ride%20Each%20Seasons.png)

A glance above shows that the most people like to ride a bike in Chicago during the summer season, with the peak number to 790,177 in August. On the other hand, the lowest rides appear during the winter season with the lowest number 138,689 in January. From the figure above, it shows that most people love to ride a bike during a friendly climate.
The next analysis is about the type of the bikes for all member and casual riders for the whole year. Apparently, the pie charts below show that ??% rode an electric bike, and the rest ??% rode classic bikes.  

### Comparison Behavior
In order to understand the difference between the member and casual riders, the next analysis is comparing the data between member and casual riders. 
Starting with the total ride between them in each season, the two figures below show the total count with bar graphs, respectively for casual in blue color and member in orange color.
