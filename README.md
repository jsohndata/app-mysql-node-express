## Create Database
```
CREATE DATABASE node_mysql2;
```

## Create Table
```
CREATE TABLE IF NOT EXISTS about_people (
	id INT AUTO_INCREMENT UNIQUE NOT NULL,
	person_id CHAR(6) NOT NULL UNIQUE,

	name_f VARCHAR(100) NOT NULL,
	name_m VARCHAR(100) NOT NULL,
	name_l VARCHAR(100) NOT NULL,
	age INT NOT NULL DEFAULT 1,
	bio TEXT,
	profile_pict TINYTEXT,
	register BOOLEAN,

	date_insert TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
	PRIMARY KEY (person_id)
);
```

## Insert into Table
```
INSERT INTO about_people (id, person_id, name_f, name_m, name_l, age, bio, profile_pict, register) VALUES (
	0,
	"PID010",
	"John",
	"",
	"Dough",
	1338,
	"resident at JH",
	"https://prod-api.154310543964.hellopublic.com/static/users/images/1ovWcBG0YFiYtYZ7pS5qM2Nj6YmzAwBY-thumbnail-300x300.jpg",
	true
),

(
	0,
	"PID007",
	"Slack",
	"",
	"Bot",
	999,
	"lol computer",
	"https://prod-api.154310543964.hellopublic.com/static/users/images/1ovWcBG0YFiYtYZ7pS5qM2Nj6YmzAwBY-thumbnail-300x300.jpg",
	true
);
```


## SELECT *
`SELECT * FROM about_people;`

## SELECT COL
`SELECT id, date_insert, person_id, name_f, name_m, name_l, register  FROM about_people;`

## SELECT WHERE
`SELECT person_id, name_f, name_l FROM about_people WHERE register < 1;`

## SELECT ORDER BY
`SELECT person_id, name_f, name_m, name_l, register FROM about_people  ORDER BY name_f;`

## SELECT WHERE ORER BY
`SELECT person_id, name_f, name_l FROM about_people WHERE register = 1 ORDER BY name_l;`

## SELECT WHERE ORDER BY ASC / DESC
`SELECT id, person_id, name_f, name_l FROM about_people WHERE register = 1 ORDER BY name_l ASC;`

## UPDATE WHERE
`UPDATE about_people SET name_l = "bottty" WHERE person_id = "PID005";`

## DELETE FROM WHERE
`DELETE FROM about_people WHERE person_id = "PID005";`