# Flights Delay

This is the repository for the `flights_delay` table for the lessons from data36.com

https://data36.com/sql-where-clause-tutorial-beginners-ep2/

We use the 2007 dataset only. **Go to Installation Steps to install using PGSQL database backup**

The original dataset information can be found here: https://dataverse.harvard.edu/file.xhtml?persistentId=doi:10.7910/DVN/HG7NV7/2BHLWK&version=1.0

### Data Expo 2009 - Airline on-time performance:

https://community.amstat.org/jointscsg-section/dataexpo/dataexpo2009

https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/HG7NV7

Have you ever been stuck in an airport because your flight was delayed or cancelled and wondered if you could have predicted it if you'd had more data? This is your chance to find out.

#### The results

We had a total of [nine entries](http://stat-computing.org/dataexpo/2009/posters), and turn out at the poster session at the JSM was great, with plenty of people stopping by to find out why their flights were delayed.

#### The data

The data set is available for download [here](https://doi.org/10.7910/DVN/HG7NV7).  
[The data](https://doi.org/10.7910/DVN/HG7NV7) consists of flight arrival and departure details for all commercial flights within the USA, from October 1987 to April 2008. This is a large dataset: there are nearly 120 million records in total, and takes up 1.6 gigabytes of space compressed and 12 gigabytes when uncompressed. To make sure that you're not overwhelmed by the size of the data, we've provide two brief introductions to some useful tools: [linux command line tools](http://stat-computing.org/dataexpo/2009/unix-tools.html) and [sqlite](http://stat-computing.org/dataexpo/2009/sqlite.html), a simple sql database.

#### The challenge

The aim of the data expo is to provide a **graphical** summary of important features of the data set. This is intentionally vague in order to allow different entries to focus on different aspects of the data, but here are a few ideas to get you started:

- When is the best time of day/day of week/time of year to fly to minimise delays?
- Do older planes suffer more delays?
- How does the number of people flying between different locations change over time?
- How well does weather predict plane delays?
- Can you detect cascading failures as delays in one airport create delays in others? Are there critical links in the system?

You are also welcome to work with interesting subsets: you might want to compare flight patterns before and after 9/11, or between the pair of cities that you fly between most often, or all flights to and from a major airport like Chicago (ORD). Smaller subsets may also help you to match up the data to [other interesting datasets](http://stat-computing.org/dataexpo/2009/supplemental-data.html).

### Installation

The PostgreSQL backup was created using the command: pg_dump ontimedata > ontimedata.sql

1. To install the database, at the command prompt:

psql ontimedata < ontimedata.sql

2. \c ontimedata

3. 
```
ontimedata=# \dt+
                                       List of relations
 Schema |     Name      | Type  |  Owner   | Persistence | Access method |  Size  | Description
--------+---------------+-------+----------+-------------+---------------+--------+-------------
 public | flight_delays | table | postgres | permanent   | heap          | 646 MB |
(1 row)
```

3. 
```
ontimedata=# \d flight_delays;
                  Table "public.flight_delays"
   Column   |       Type        | Collation | Nullable | Default
------------+-------------------+-----------+----------+---------
 year       | integer           |           |          |
 month      | integer           |           |          |
 dayofmonth | integer           |           |          |
 dayofweek  | integer           |           |          |
 deptime    | integer           |           |          |
 arrtime    | integer           |           |          |
 flightnum  | integer           |           |          |
 tailnum    | character varying |           |          |
 airtime    | integer           |           |          |
 arrdelay   | integer           |           |          |
 depdelay   | integer           |           |          |
 origin     | character varying |           |          |
 dest       | character varying |           |          |
 distance   | integer           |           |          |
```
