# Query con group by

1. Contare quanti iscritti ci sono stati ogni anno

SELECT YEAR(enrolment_date) AS 'enrolment_year',

COUNT(\*) AS 'number_enrolments'

FROM students

GROUP BY enrolment_year;

---

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT office_address AS 'office_building' ,

COUNT(\*) AS 'number_of_teachers'

FROM teachers

GROUP BY office_address;

3. Calcolare la media dei voti di ogni appello d'esame

4. Contare quanti corsi di laurea ci sono per ogni dipartimento
