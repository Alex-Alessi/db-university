1. Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT *
FROM `students`
WHERE `date_of_birth` >= "1990-01-01"
AND `date_of_birth` <= "1990-12-31";
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT *
FROM `courses`
WHERE `cfu`> "10";
```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT *,  TIMESTAMPDIFF(YEAR, date_of_birth, "2025-01-07")
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, date_of_birth, "2025-01-07") >="30";
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

```sql
   SELECT *
FROM `courses`
WHERE `period` = "I semestre" AND `year`=1;
```

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)

   ```sql
   SELECT *
   FROM `exams`
   WHERE `date`="2020-06-20" AND `hour` >= "14:00:00" ;
   ```

6. Selezionare tutti i corsi di laurea magistrale (38)

   ```sql
      SELECT *
      FROM `degrees`
      WHERE `level`="magistrale";
   ```

7. Da quanti dipartimenti è composta l'università? (12)

```sql
   SELECT * FROM `departments`;
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
   SELECT *
   FROM `teachers`
   WHERE `phone` IS NULL;
```

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
   degree_id, inserire un valore casuale)

   ```sql
   INSERT INTO `students` (degree_id, name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number, email)
   VALUES ('75', 'Alex', 'Alessi', '2002-04-06', 'LSSLXA02', '2025-01-07', '630000', 'alex.alessi@gmail.com');
   ```

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

```sql
UPDATE `teachers`
SET `office_number` = 126
WHERE `name` = 'Pietro' AND `surname`="Rizzo";
```

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```sql
DELETE FROM `students`
WHERE `fiscal_code`="LSSLXA02";
```
