# dlt

Q1: dlt 1.6.1

import dlt
print("dlt version:", dlt.__version__)


Q2: 4
# Describe the dataset
conn.sql("DESCRIBE").df()

Q3. 10000
df = pipeline.dataset(dataset_type="default").rides.df()
df

Q4. 12.3049
with pipeline.sql_client() as client:
    res = client.execute_sql(
            """
            SELECT
            AVG(date_diff('minute', trip_pickup_date_time, trip_dropoff_date_time))
            FROM rides;
            """
        )
    # Prints column values of the first row
    print(res)