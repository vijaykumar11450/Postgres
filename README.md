# pgopensv-analytics-tutorial
### Clone the repository
Downloads all the scripts and data needed for the tutorial.
  ```bash
  git clone https://github.com/citusdata/pgopensv-analytics-tutorial.git
  cd pgopensv-analytics-tutorial 
  ``` 
### Schema
Schema has 3 main tables
* **events**: raw table which captures every event.
* **rollup\_5mins**: table to store aggregated data every 5-minute intervals.
* **rollup\_1hr**:   table to store aggregated data every 1-hour. <br />
Connect to postgres via psql and run the below command to create the above tables. <br />
Also note that we are sharding each of the tables on tenant\_id column. Hence they are colocated. <br />
```bash
\i schema.sql
```
\i schema.sql<br />

<br />
\i refresh.sql<br />
\i schema.sql<br />
\i setup\_rollup.sql<br />
\i 5minutely\_aggregation.sql<br />
\i hourly\_aggregation.sql<br />
\COPY events(customer\_id,event\_type,country,browser,device\_id,session\_id) FROM data/1.csv WITH (FORMAT CSV,HEADER TRUE);
SELECT hourly\_aggregation();
SELECT five\_minutely\_aggregation();
