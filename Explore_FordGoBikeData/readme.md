# Ford GoBike Data Exploration
## by Jing Lu


## Dataset

The data, provided by Ford GoBike, a bike-sharing system, contains information of rides in the greater San Francisco Bay area. 
Each trip includes:
* User info: type, gender, birth-year
* Time info: start time, end time, duration in seconds
* Location info: start/end station id/name/longitude/longitude
The history data is availale at [Ford GoBike website] (https://s3.amazonaws.com/fordgobike-data/index.html)

## Summary of Findings
My exploration is around of the following questions
### Demographics of users
1. About 73.5% users are male, 25% are female, and 1.5% are other.
2. About 89% users are subscribers.
3. About 99% user <= 65 years old.
### Distribution of trip duration
1. 78.4% trips are within 15 minutes, %96 trips are within 30 minutes, 98.9% trips are within 60 minutes which aligns well with the system's desgin goal: as an alternative to motorised public transport or private vehicles for short-distance trips in urban area  
2. Looking across two types of users (Customer and Subscriber): customers take longer trips than subscribers 
### User activity level over time
1. Users are most active in 8:00 - 9:00, 17:00 - 18:00, followed by 9:00AM - 10:00AM, 18:00 - 19:00, and then 16:00 - 17:00 - those are rush hours.
2. Users are more active on weekdays than weekends.
3. Activities increase when weather gets warmer, reach and keep at a stable level during summer, climb to the peak around Oct, and then decrease as weather turns colder.
4. Looking across two types of users (Customer and Subscriber): The Subscriber group follows the pattern on the entire dataset tightly (in all three granularities: hour of day, day of week, month of year.
### Most taken trips
1. I first started with defining a trip by pair of start station and end station and found out that with this definition, top 20 trips only counts for 3.55% of total trips.
2. Then by start station: top 20 trips count for 28.05% of total trips
3. Then by end station: top 20 trips count for 30.27% of total trips.
4. Finally, I use the total traffic to measure how busy a station is, i.e., the total number of bike pick up and bike return: top 20 trips counts for 29.15% of total trips. 
5. Looking across two types of users (Customer and Subscriber): The Subscriber group follows the pattern on the entire dataset more closely than the Customer group.

## Key Insights for Presentation
Based on the above analysis, we can see that 
1. The system's behavioral patterns are primarily driven by subscribers in lots of aspects: trip duration, most taken trips, user activiy level over time and etc. After all, subscribers counts for 89% of users.
2. The above observation aligns with the system's design goal: as an alternative to motorised public transport or private vehicles for short-distance trips in urban area. The main consumers are people who are living and/or working in the area - they have more stable routes and schedules compared with customers, who might be tourists, or people occasionally visit the area ...