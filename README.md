# Call Center Data Analytics Dashboard for PhoneNow

### Project Overview 


PhoneNow’s Call Center Manager, Claire, seeks a Power BI dashboard for comprehensive insights into call center operations. The dashboard will visualize KPIs like customer satisfaction, calls answered/abandoned, call volume trends, average speed of answer, and agent performance. The goal is to provide clear, actionable data for management discussions.
<img width="545" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/6fa4e7f0-25e1-4e23-9022-fde80db83794">

### Data Sources :
- Call Center Data: The primary dataset for this analysis is the "call_center.csv" file, which contains comprehensive details on each call handled by the company. This 
  dataset will be used to generate key performance indicators (KPIs) to provide insights into overall call center performance, customer satisfaction, call handling 
  efficiency, and agent productivity. The resulting Power BI dashboard will enable PhoneNow’s Call Center Manager, Claire, to make informed decisions and drive improvements in 
  call center operations.

  <img width="581" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/bad6f23c-5f5e-4abc-9855-a30a30ff5f28">

### Tools
- Excel - Data cleaning and Data Standardization
- SQL Server - Data analysis
- Power BI - creating a reports
### KPI'S

1. Overall Customer Satisfaction
     ```
         SELECT Agent, ROUND(AVG([Satisfaction rating]),2) AS avg_Satisfaction_rating
         FROM call_center
         GROUP BY Agent; ```
### output
<img width="167" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/d41b9748-1c19-420d-8bfe-87dc3f57789a">
2. Calls by time
    '''
    
        select  datename(month,Date ) as Month  , count(distinct [Call Id]) as [number of calls] , 
        [Answered (Y/N)]
        from Call_center 
        group by datename(month,Date ) , [Answered (Y/N)];
        '''
### output 
<img width="220" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/bbc1d8b5-fbfb-47b8-b8be-90980fe3f86d">

3. Overall calls Answered 
     ``` 
     
        SELECT Agent, 
             COUNT(DISTINCT CASE WHEN [Answered (Y/N)] = 'Y' THEN [Call Id] ELSE NULL END) AS answered
        FROM  call_center
        GROUP BY  Agent;
        '''

### output
<img width="122" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/48e8409f-8305-4a31-bfcc-f32f8d1e1664">

4. Average speed of answer
```
      select Agent ,round(AVG([Speed of answer in seconds]),2) as spped_in_sec
      from call_center 
      group by Agent;
   ```
### output
<img width="144" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/03ab9221-72d4-4635-9314-080561c514f5">

5. overall problems in calls resolved
   ``` SELECT 
    Agent, 
    COUNT(DISTINCT CASE WHEN Resolved = 'Y' THEN [Call Id] ELSE NULL END) AS Resolved
   FROM Call_center
   GROUP BY Agent;
   ```
### output
<img width="119" alt="image" src="https://github.com/muralikatta12/Call-Center-Data-Analytics-Dashboard-for-PhoneNow/assets/124357793/02bdf72a-acbd-4f0e-9a9f-2017f898d8a3">

### Findings from Pizza Sales Analysis

- The highest number of calls per month was recorded in January, totaling 1455 calls.

- In January, all 1455 calls were answered.

- Additionally, there were 317 calls in January that were not answered.

- The majority of the calls that were answered and resolved were handled by the agent **Jim**.









  
