![quinta exericse](quinta.png)

• `SQL` (Structured Query Language) est le langage standard pour interagir avec une base de données. Il est utilisé par tous les SGBD.
• Un `SGBD` est un logiciel de gestion de base de données, qui utilise donc SQL.
• `MySQL` est un SGBD très utilisé, appartenant à l'entreprise Oracle. 

**Création de la base de donnée :**

 ```mysql> CREATE DATABASE quinta; ```

  ```mysql> USE quinta; ```

**Création des tables :** 

```sql
mysql> CREATE TABLE city (
    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    ->     name VARCHAR(100) NOT NULL,
    ->     lat FLOAT NOT NULL,
    ->     lon FLOAT NOT NULL
    -> );
```

```sql
mysql> CREATE TABLE people (
    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    ->     name VARCHAR(100) NOT NULL,
    ->     dob DATE NOT NULL,
    ->     height FLOAT NOT NULL,
    ->     city_id INT,
    ->     FOREIGN KEY (city_id) REFERENCES city(id)
    -> );
``` 

**Remplissage des tables avec des données :** 

```sql
mysql> INSERT INTO people (name, dob, height, city_id) 
    -> VALUES 
    ->     ('Bonbby', '1985-08-25', 1.80, 1),
    ->     ('Charlie', '1992-03-12', 1.75, 2),
    ->     ('Diane', '1995-07-14', 1.60, 3),
    ->     ('Evan', '1989-11-30', 1.70, 2),
    ->     ('Frank', '1987-06-02', 1.85, 1),
    ->     ('Grace', '1991-09-18', 1.68, 4),
    ->     ('Henry', '1984-12-05', 1.90, 1),
    ->     ('Isabelle', '1993-04-21', 1.62, 3),
    ->     ('Jack', '1994-05-09', 1.72, 4),
    ->     ('Kate', '1986-02-14', 1.67, 2),
    ->     ('Leonardo', '1990-08-30', 1.83, 1),
    ->     ('Maria', '1988-10-22', 1.65, 4),
    ->     ('Nina', '1996-03-16', 1.55, 3),
    ->     ('Oscar', '1997-07-04', 1.78, 2),
    ->     ('Paul', '1983-11-19', 1.80, 1),
    ->     ('Quinn', '1992-05-25', 1.68, 3),
    ->     ('Rick', '1994-12-01', 1.79, 2),
    ->     ('Sophie', '1991-01-27', 1.65, 4),
    ->     ('Tommy', '1985-09-09', 1.82, 1),
    ->     ('Umah', '1990-04-18', 1.58, 3);
```
```sql
INSERT INTO city (name, lat, lon) VALUES ('Lille', 22.688, 8.3344) ('Lyon', 77.666, 1.4444) ('Paris', 45.666, 2.4444) ('Toulouse', 66.666, 5.4444);
```

**Récupérer la liste de toutes les personnes triées de la plus vieille à la plus jeune :** 

```sql
SELECT * FROM people 
    -> ORDER BY dob ASC;
+----+----------+------------+--------+---------+
| id | name     | dob        | height | city_id |
+----+----------+------------+--------+---------+
| 37 | Paul     | 1983-11-19 |    1.8 |       1 |
| 29 | Henry    | 1984-12-05 |    1.9 |       1 |
| 23 | Bonbby   | 1985-08-25 |    1.8 |       1 |
| 41 | Tommy    | 1985-09-09 |   1.82 |       1 |
| 32 | Kate     | 1986-02-14 |   1.67 |       2 |
| 27 | Frank    | 1987-06-02 |   1.85 |       1 |
| 34 | Maria    | 1988-10-22 |   1.65 |       4 |
| 26 | Evan     | 1989-11-30 |    1.7 |       2 |
| 42 | Umah     | 1990-04-18 |   1.58 |       3 |
|  1 | Alice    | 1990-05-10 |   1.65 |       1 |
| 33 | Leonardo | 1990-08-30 |   1.83 |       1 |
| 22 | Bonbby   | 1990-09-10 |   1.65 |       1 |
| 40 | Sophie   | 1991-01-27 |   1.65 |       4 |
| 28 | Grace    | 1991-09-18 |   1.68 |       4 |
| 24 | Charlie  | 1992-03-12 |   1.75 |       2 |
| 38 | Quinn    | 1992-05-25 |   1.68 |       3 |
| 30 | Isabelle | 1993-04-21 |   1.62 |       3 |
| 31 | Jack     | 1994-05-09 |   1.72 |       4 |
| 39 | Rick     | 1994-12-01 |   1.79 |       2 |
| 25 | Diane    | 1995-07-14 |    1.6 |       3 |
| 35 | Nina     | 1996-03-16 |   1.55 |       3 |
| 36 | Oscar    | 1997-07-04 |   1.78 |       2 |
+----+----------+------------+--------+---------+
```



**Récupérer la liste de toutes les personnes triées de la plus petite à la plus grande :** 

```sql
SELECT * FROM people 
    -> ORDER BY height ASC;
+----+----------+------------+--------+---------+
| id | name     | dob        | height | city_id |
+----+----------+------------+--------+---------+
| 35 | Nina     | 1996-03-16 |   1.55 |       3 |
| 42 | Umah     | 1990-04-18 |   1.58 |       3 |
| 25 | Diane    | 1995-07-14 |    1.6 |       3 |
| 30 | Isabelle | 1993-04-21 |   1.62 |       3 |
|  1 | Alice    | 1990-05-10 |   1.65 |       1 |
| 22 | Bonbby   | 1990-09-10 |   1.65 |       1 |
| 34 | Maria    | 1988-10-22 |   1.65 |       4 |
| 40 | Sophie   | 1991-01-27 |   1.65 |       4 |
| 32 | Kate     | 1986-02-14 |   1.67 |       2 |
| 28 | Grace    | 1991-09-18 |   1.68 |       4 |
| 38 | Quinn    | 1992-05-25 |   1.68 |       3 |
| 26 | Evan     | 1989-11-30 |    1.7 |       2 |
| 31 | Jack     | 1994-05-09 |   1.72 |       4 |
| 24 | Charlie  | 1992-03-12 |   1.75 |       2 |
| 36 | Oscar    | 1997-07-04 |   1.78 |       2 |
| 39 | Rick     | 1994-12-01 |   1.79 |       2 |
| 23 | Bonbby   | 1985-08-25 |    1.8 |       1 |
| 37 | Paul     | 1983-11-19 |    1.8 |       1 |
| 41 | Tommy    | 1985-09-09 |   1.82 |       1 |
| 33 | Leonardo | 1990-08-30 |   1.83 |       1 |
| 27 | Frank    | 1987-06-02 |   1.85 |       1 |
| 29 | Henry    | 1984-12-05 |    1.9 |       1 |
+----+----------+------------+--------+---------+
```

**Récupérer la liste de toutes les personnes triées avec le nom de leurs villes de naissance :**

```sql
SELECT people.name, people.dob, people.height, city.name AS city_name 
    -> FROM people 
    -> JOIN city ON people.city_id = city.id;
+----------+------------+--------+-----------+
| name     | dob        | height | city_name |
+----------+------------+--------+-----------+
| Alice    | 1990-05-10 |   1.65 | Toulouse  |
| Bonbby   | 1990-09-10 |   1.65 | Toulouse  |
| Bonbby   | 1985-08-25 |    1.8 | Toulouse  |
| Frank    | 1987-06-02 |   1.85 | Toulouse  |
| Henry    | 1984-12-05 |    1.9 | Toulouse  |
| Leonardo | 1990-08-30 |   1.83 | Toulouse  |
| Paul     | 1983-11-19 |    1.8 | Toulouse  |
| Tommy    | 1985-09-09 |   1.82 | Toulouse  |
| Charlie  | 1992-03-12 |   1.75 | Paris     |
| Evan     | 1989-11-30 |    1.7 | Paris     |
| Kate     | 1986-02-14 |   1.67 | Paris     |
| Oscar    | 1997-07-04 |   1.78 | Paris     |
| Rick     | 1994-12-01 |   1.79 | Paris     |
| Diane    | 1995-07-14 |    1.6 | Lyon      |
| Isabelle | 1993-04-21 |   1.62 | Lyon      |
| Nina     | 1996-03-16 |   1.55 | Lyon      |
| Quinn    | 1992-05-25 |   1.68 | Lyon      |
| Umah     | 1990-04-18 |   1.58 | Lyon      |
| Grace    | 1991-09-18 |   1.68 | Lille     |
| Jack     | 1994-05-09 |   1.72 | Lille     |
| Maria    | 1988-10-22 |   1.65 | Lille     |
| Sophie   | 1991-01-27 |   1.65 | Lille     |
+----------+------------+--------+-----------+
```
**Récupérer la liste de toutes les personnes regroupées par villes :**
```sql
SELECT city.name AS city_name, GROUP_CONCAT(people.name) AS people_names
    -> FROM people 
    -> JOIN city ON people.city_id = city.id
    -> GROUP BY city.name;
+-----------+-----------------------------------------------------+
| city_name | people_names                                        |
+-----------+-----------------------------------------------------+
| Lille     | Grace,Jack,Maria,Sophie                             |
| Lyon      | Diane,Isabelle,Nina,Quinn,Umah                      |
| Paris     | Charlie,Evan,Kate,Oscar,Rick                        |
| Toulouse  | Alice,Bonbby,Bonbby,Frank,Henry,Leonardo,Paul,Tommy |
+-----------+-----------------------------------------------------+
```

**Récupérer la liste de toutes les personnes triées par celle qui est née le plus proche de Toulouse à celle qui est née le plus loin :**

Ps : Les données `longitude`et `latitude` sont au pif donc le résultat : Paris est proche de Toulouse est juste dans la logique de l'exercice mais faux dans ka réalité ...
```sql
SELECT people.name, city.name AS city_name,
    ->     ( 6371 * ACOS( COS( RADIANS(66.666) ) 
    ->     * COS( RADIANS(city.lat) ) 
    ->     * COS( RADIANS(city.lon) - RADIANS(5.4444) ) 
    ->     + SIN( RADIANS(43.6045) ) 
    ->     * SIN( RADIANS(city.lat) ) ) ) AS distance_to_toulouse
    -> FROM people
    -> JOIN city ON people.city_id = city.id
    -> ORDER BY distance_to_toulouse ASC;
+----------+-----------+----------------------+
| name     | city_name | distance_to_toulouse |
+----------+-----------+----------------------+
| Alice    | Toulouse  |   4203.1531695586245 |
| Bonbby   | Toulouse  |   4203.1531695586245 |
| Bonbby   | Toulouse  |   4203.1531695586245 |
| Frank    | Toulouse  |   4203.1531695586245 |
| Henry    | Toulouse  |   4203.1531695586245 |
| Leonardo | Toulouse  |   4203.1531695586245 |
| Paul     | Toulouse  |   4203.1531695586245 |
| Tommy    | Toulouse  |   4203.1531695586245 |
| Charlie  | Paris     |   4411.0925748613445 |
| Evan     | Paris     |   4411.0925748613445 |
| Kate     | Paris     |   4411.0925748613445 |
| Oscar    | Paris     |   4411.0925748613445 |
| Rick     | Paris     |   4411.0925748613445 |
| Diane    | Lyon      |    4525.374766254204 |
| Isabelle | Lyon      |    4525.374766254204 |
| Nina     | Lyon      |    4525.374766254204 |
| Quinn    | Lyon      |    4525.374766254204 |
| Umah     | Lyon      |    4525.374766254204 |
| Grace    | Lille     |    5657.219068511048 |
| Jack     | Lille     |    5657.219068511048 |
| Maria    | Lille     |    5657.219068511048 |
| Sophie   | Lille     |    5657.219068511048 |
+----------+-----------+----------------------+
```

