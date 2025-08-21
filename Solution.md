 ```sql

WITH total_events AS (SELECT COUNT(DISTINCT(event_name)) AS total_event
					         FROM events
					 ),
							
	events_attended AS (SELECT e.emp_id,
			                   n.name,
			                   COUNT(DISTINCT(e.event_name)) AS event_att
				            FROM events AS e
                            JOIN employees AS n ON e.emp_id = n.id
				            GROUP BY e.emp_id, n.name
					    )
				  
	SELECT a.name AS employee_name,
	      a.event_att AS no_of_events
		  FROM events_attended AS a
		   CROSS JOIN total_events AS te
		  WHERE a.event_att = te.total_event;
```

| employee_name | no_of_events |
|---------------|--------------|
| Charles |	3 |
| Sainz |	3 |
