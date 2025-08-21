# TechTFQ_SQL_Interview_Query_18

Find out the employees who attended all company events

```sql

drop table if exists employees;
create table employees
(
	id			int,
	name		varchar(50)
);
insert into employees values(1, 'Lewis');
insert into employees values(2, 'Max');
insert into employees values(3, 'Charles');
insert into employees values(4, 'Sainz');


drop table if exists events;
create table events
(
	event_name		varchar(50),
	emp_id			int,
	dates			date
);
insert into events values('Product launch', 1, to_date('01-03-2024','DD-MM-YYYY'));
insert into events values('Product launch', 3, to_date('01-03-2024','DD-MM-YYYY'));
insert into events values('Product launch', 4, to_date('01-03-2024','DD-MM-YYYY'));
insert into events values('Conference', 2, to_date('02-03-2024','DD-MM-YYYY'));
insert into events values('Conference', 2, to_date('03-03-2024','DD-MM-YYYY'));
insert into events values('Conference', 3, to_date('02-03-2024','DD-MM-YYYY'));
insert into events values('Conference', 4, to_date('02-03-2024','DD-MM-YYYY'));
insert into events values('Training', 3, to_date('04-03-2024','DD-MM-YYYY'));
insert into events values('Training', 2, to_date('04-03-2024','DD-MM-YYYY'));
insert into events values('Training', 4, to_date('04-03-2024','DD-MM-YYYY'));
insert into events values('Training', 4, to_date('05-03-2024','DD-MM-YYYY'));


select * from employees;
```

| id | name |
|----|------|
| 1	 | Lewis |
| 2	 | Max |
| 3	 | Charles |
| 4	 | Sainz |

```sql

select * from events;
```

| event_name | emp_id | dates |
|------------|--------|-------|
| Product launch | 1 | 2024-03-01 |
| Product launch | 3 | 2024-03-01 |
| Product launch | 4 | 2024-03-01 |
| Conference | 2	 | 2024-03-02 |
| Conference | 2	 | 2024-03-03 |
| Conference	| 3	 | 2024-03-02 |
| Conference | 4	 | 2024-03-02 |
| Training | 3	 | 2024-03-04 |
| Training | 2	| 2024-03-04 |
| Training | 4	 | 2024-03-04 |
| Training | 4	| 2024-03-05 |
