## Overview

![Untitled design](https://github.com/theliwash/Toman-Bike-Share-Metrics-Dashboard-for-Data-Driven-Decisions/assets/163035610/5efd7fd2-57e1-4e24-bf7f-8a4a46a2b0a4)


This repository contains the code and resources for developing a dashboard for "Toman Bike Share." The dashboard aims to display key performance metrics to facilitate informed decision-making within the organization.

## Tech Stack
- **SQL:** Data is queried and manipulated using SQL for database operations in this dashboard development. 

- **Power BI:** The dashboard is developed using Power BI for data visualization and analysis.

## Data Source
The necessary datasets can be found in the link given below:
https://github.com/Gaelim/YT_bike_share

## SQL Code
Below is the snippet of the SQL query used to create a new table for dashboard development:
```sql
with cte as (
select * from bike_share_yr_0
union all
select * from bike_share_yr_1)

select
dteday,
season,
a.yr,
weekday,
hr,
rider_type,
riders,
price,
COGS,
riders * price as revenue,
riders * price - COGS as profit
from cte a
left join cost_table b
on a.yr = b.yr
```

## Features
- **Total Riders and Profitability:** The bike-sharing service has 3 million riders with a profit margin of 45.4%.
- **Financial Performance:** Total profit is $10.45 million, and total revenue is $15 million.
- **Seasonal Revenue:** Highest revenue in season 3 ($4.9 million) and lowest in season 1 ($2.2 million).
- **Rider Demographics:** 81.17% are registered riders, and 18.83% are casual riders.
- **Hourly Revenue Analysis:** The table shows hourly revenue from 8 AM to 8 PM across the week. Tuesday is the busiest and most profitable day, especially at 12 PM and 5 PM, with earnings of $1,222 and $1,254 respectively. The most profitable times across the week are 8 AM on Thursday, 9 AM on Friday, 12 PM on Monday, 5 PM on Tuesday, and 7 PM on Tuesday. These times show the highest revenue for the bike-sharing service.



## Recommendations
### Pricing Strategy
- **Conservative Increase:** Considering the substantial increase last year, a more conservative increase might be prudent to avoid hitting a price ceiling where demand starts to drop. An increase in the range of 10-15% could test the market's response without risking a significant loss of customers.
- **Price Setting:** If the price in 2022 was $4.99, a 10% increase would make the new price about $5.49, while a 15% increase would set the price at approximately $5.74.
- **Recommended Strategy:**
  - **Market Analysis:** Conduct further market research to understand customer satisfaction, potential competitive changes, and the overall economic environment. This can guide whether leaning towards the lower or higher end of the suggested increase.
  - **Segmented Pricing Strategy:** Consider different pricing for casual versus registered users, as they may have different price sensitivities.
  - **Monitor and Adjust:** Implement the new prices but be ready to adjust based on immediate customer feedback and sales data. Monitoring closely will allow you to fine-tune your pricing strategy without committing fully to a price that might turn out to be too high.
 
## Final Dashboard

![Screenshot (28)](https://github.com/theliwash/Toman-Bike-Share-Metrics-Dashboard-for-Data-Driven-Decisions/assets/163035610/8aad75de-c3e1-46e5-b79d-932912c7ec3f)


## Usage
- Clone the repository to your local machine.
- Set up the necessary environment and dependencies.
- Run the dashboard application.
