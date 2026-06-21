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
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/e5c2daa7c1fd5da472288972f6a2a719c28b24a4/Total%20Ride%20Each%20Type%20Bike.png)

### Comparison Behavior
In order to understand the difference between the member and casual riders, the next analysis is comparing the data between member and casual riders. 
Starting with the total ride between them in each season, the two figures below show the total count with bar graphs, respectively for casual in blue color and member in orange color.
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/0b3d2a27ba630d729bd49689c56925bf39992581/Total%20Ride%20Each%20Seasons%20for%20Member%20and%20Casual.png)

Based on the graphs above, the trends of two types of riders both similar to each other, the number increase dramatically during the summer season with both reaching their peak in August. Also, the fall trend drastically appears for both types during the colder season, with casual riders in January and member riders in December. 

![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/a95c16ce9a0179274def6d3dc2f117da54a9c243/Peak%20Hour%20for%20Each%20Member%20and%20Casual.png)

Considering the behavior of both types of riders, data about the time each type started to ride the bikes was collected for total rides in each hour a day . Based on the figure above it shows that before 12 am, most of the member riders rode the bike at 8 am, after noon time the number reached the peak hours at 5 pm. It shows that the characteristic for most of the member riders is using a bike for work. For the casual riders, the two highest number of riders reached not in the morning, with the most at 5 pm same as the member riders, and the second highest at 12 am.
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/cf388cb952a2ab64581e02bdcc16dc7a4ae6b35b/Average%20Casual%20Daily%20RIdes.png)
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/e3921dc5f93f690c478d03c2ec2a93d726f3c58f/Average%20Member%20Daily%20Rides.png)

The next behavior observation is regarding their weekly rides. Two figures above showed the average for both types in a week. For the casual riders, they tend to ride a bike during the weekend, with the highest number of rides on Saturday. For the member riders graph, the trends showed most of the members commuted during the weekdays, with the total rides reaching over ten thousand on weekdays, with the highest number on Thursday.
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/5f51d8e98cd778e29a62f5dd5e67b7c4a9d37370/Top%20Start%20and%20End%20Station%20in%20Each%20Seasons%20for%20Member%20Rider.png)
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/ca725c00bf1b04efc529916ec35a0be5d468f69f/Top%20Start%20and%20End%20Station%20in%20Each%20Seasons%20for%20Casual%20Ride.png)

Also, for the further understanding of the behavior the both types of riders, conduct the count of the location of the starting and ending stations. For the two figures above, apparently the member rider has consistent results shown in three seasons from  Spring to Fall with starting and ending stations at the same locations at Kingsbury St and Kinzie St. Although the results for casual riders are more diverse with three different stations, it turns out the Navy Pier station and Streeter Dr & Grand Ave station have the same latitude and longitude points as shown at table 1.3. So the casual riders tend to like start and end their ride at Navy Pier or Streeter Dr & Grand Ave station, but during the Summer time, the starting station move to DuSable Lake Shore Dr & Monroe St. 

![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/bd36ad010c3731a031e54b77894a63a967fdd749/Map%20for%202%20most%20stations%20for%20casual.png)
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/c3b1b89cda29224171be211a62452344c1ece7b0/Map%20for%202%20most%20stations%20for%20member.png)

Based on the location of the stations, the casual riders tend to like to ride a bike around the lake area, contrast with the member riders, the two stations are around the pedestrian area and business district as shown at map figures below:
![image](https://github.com/alfinkl/Google_Data_Analytics_Capstone_Cyclistic/blob/f649a50d594faf492cacee0abdb377d04102cae1/Navy%20Pier%20and%20Streeter%20lat%20and%20lng.png)

The last figure is analyzing the different ride duration between both types. From the table above, the casual riders tend to ride longer than the member riders, with average ride approximately from fifteen minutes in the Winter season to the longest duration being twenty four minutes ride during the Summer. On the other hand, the member riders approximately only spent ten to thirteen minutes riding for the whole year.

## Insight
	According to the analysis process above, both types have similar trends, such as the highest number of rides reached during the Summer season, and also the least riders during the Winter season. Most member and casual riders tend to ride a bike at 5 pm as their preferred hours during the day. 

Casual|Member|
|------|------|
|Tend to ride during the weekend in Spring and Summer for leisure activity|Use a bike while the working hours (8am and 5pm) during the weekdays in Spring and Summer|
|Commuted longer duration than member riders|Commute more frequently than casual riders|
|Most of the start and end stations around recreational areas such as lake sites|The start and end stations close to residential areas and business district|
![image]

After all the insight found from the analysis and sorting it into the diagram above, those similarities between member and casual riders could be an element that the marketing team focuses on for their campaign strategy.
Suggestions
Based on all the circumstances that were found from identifying and analyzing the behavior for both types of riders, three suggestions could be given to the marketing team in order to achieve the target, which is to persuade the casual member to purchase the membership of cyclistic. 

|The Annual Membership|Summer Membership/3 Months Membership|Lake Membership/Monthly Membership|
|---------------------|-------------------------------------|----------------------------------|
|First-month free|Unlimited ride for 3 months|Unlimited ride for 3 months|Free ride for certain stations around the lake|
|Unlimited ride for classic and electric bike|Free use for all types of bike|Free use for all types of bike|
|Lower the price from current price by 10%|	Extra 2 days of weekends, so its 3 months + 2 days of weekend|Charge for 10% current annual member price|	
||Boost the marketing campaigns for the Summer recreational in Chicago|Boost the marketing campaigns for the lake tour, and introduce attractions around the stations|
||Charge for 25% of annual member price||







