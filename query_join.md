# Query con join

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT  
`students`.`id` AS `student_id`,

`students`.`name` AS `student_name`,

`students`.`surname`AS `student_surname`,

`degrees`.`name` AS `degree_name`

FROM `students`

INNER JOIN `degrees`

ON `degrees`.`department_id` = `students`.`degree_id`

WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

---

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

SELECT

`degrees`.`level` AS `degrees_level`,

`degrees`.`name` AS `degrees_name`,

`degrees`.`id` AS `degrees_id`,

`departments`.`name` AS `departments_name`

FROM `degrees`

INNER JOIN `departments`

ON `departments`.`id` = `degrees`.`department_id`

WHERE `degrees`.`level` = 'magistrale' AND `departments`.`name` = 'Dipartimento di Neuroscienze';

---

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT

`teachers`.`id` AS "teacher_id",

`teachers`.`name` AS "teacher_name",

`teachers`.`surname` AS "teacher_surname",

`courses`.\*

FROM `courses`

INNER JOIN `course_teacher`

ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `teachers`

ON `course_teacher`.`teacher_id` = `teachers`.`id`

WHERE `teachers`.`id` = 44;

---

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT

`students`.`id` AS "student_id",

`students`.`surname` AS "student_surname",

`students`.`name` AS "student_name",

`degrees`.\*,

`departments`.`name` AS "departmants_name"

FROM `students`

INNER JOIN `degrees`

ON `degrees`.`id` = `students`.`degree_id`

INNER JOIN `departments`

ON `departments`.`id` = `degrees`.`department_id`

ORDER BY `students`.`surname`, `students`.`name` ASC;

---

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT

`degrees`.\*,

`teachers`.`name` AS "teacher_name" ,

`teachers`.`surname` AS "teacher_surname",

`courses`.`name` AS "course_name"

FROM `degrees`

INNER JOIN `courses`

ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `course_teacher`

ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`

ON `course_teacher`.`teacher_id` = `teachers`.`id`;

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

SELECT DISTINCT

`teachers`.\*,

`departments`.`name` AS "department_name"

FROM `teachers`

INNER JOIN `course_teacher`

ON `teachers`.`id` = `course_teacher`.`teacher_id`

INNER JOIN `courses`

ON `course_teacher`.`course_id` = `courses`.`id`

INNER JOIN `degrees`

ON `courses`.`degree_id` = `degrees`.`id`

INNER JOIN `departments`

ON `degrees`.`department_id` = `departments`.`id`

WHERE `departments`.`name` = "Dipartimento di Matematica";
