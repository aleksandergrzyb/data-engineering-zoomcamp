# Question 3:

```
SELECT *
FROM "green_tripdata_2019-01" AS GT
WHERE LPEP_PICKUP_DATETIME >= timestamp '2019-01-15 00:00:00'
	AND LPEP_PICKUP_DATETIME < timestamp '2019-01-16 00:00:00'
	AND LPEP_DROPOFF_DATETIME >= timestamp '2019-01-15 00:00:00'
	AND LPEP_DROPOFF_DATETIME < timestamp '2019-01-16 00:00:00'
	AND LPEP_PICKUP_DATETIME <= LPEP_DROPOFF_DATETIME
```

# Question 4:

```
SELECT *
FROM "green_tripdata_2019-01" AS GT
ORDER BY TRIP_DISTANCE DESC
```

# Question 5:

```
SELECT *
FROM "green_tripdata_2019-01"
WHERE LPEP_PICKUP_DATETIME >= timestamp '2019-01-01 00:00:00'
	AND LPEP_PICKUP_DATETIME < timestamp '2019-01-02 00:00:00'
	AND PASSENGER_COUNT = 2
```

```
SELECT *
FROM "green_tripdata_2019-01"
WHERE LPEP_PICKUP_DATETIME >= timestamp '2019-01-01 00:00:00'
	AND LPEP_PICKUP_DATETIME < timestamp '2019-01-02 00:00:00'
	AND PASSENGER_COUNT = 3
```

# Question 6:

```
SELECT TRIP_DISTANCE,
	PUZ."Zone" AS PICK_UP_ZONE,
	GT."PULocationID",
	DOZ."Zone" AS DROPOFF_ZONE,
	GT."DOLocationID"
FROM "green_tripdata_2019-01" AS GT
JOIN PUBLIC.ZONES AS PUZ ON GT."PULocationID" = PUZ."LocationID"
JOIN PUBLIC.ZONES AS DOZ ON GT."DOLocationID" = DOZ."LocationID"
WHERE PUZ."Zone" = 'Astoria'
ORDER BY TRIP_DISTANCE DESC
```

The drop off location for the largest trip gives me `null`, so now answer matches. 🤔

Thank you for the course, it's great!
