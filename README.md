SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990;

SELECT * FROM `courses` WHERE `cfu` > 10;

SELECT * 
FROM `students` 
WHERE TIMESTAMPDIFF(YEAR,`date_of_birth`,CURDATE()) > 30;

SELECT* FROM `courses` WHERE `period` = 'I semestre' AND `year` = 1;

SELECT * FROM `exams` WHERE `date` = '2020-06-20' AND HOUR(`hour`) >= 14;

SELECT * FROM `degrees` WHERE `level` = 'magistrale';

SELECT COUNT(*) AS`n_depart` 
FROM `departments`

SELECT COUNT(*) AS`n_insegnanti` FROM `teachers` WHERE `phone` IS NULL;




SELECT COUNT(id),YEAR(`enrolment_date`) AS year_enrolment FROM `students` GROUP BY `year_enrolment`;



****************************************
****************************************


07/02


SELECT COUNT(`id`), `office_address` FROM `teachers` GROUP BY `office_address` ORDER BY `office_address` ASC;
SELECT COUNT(`id`) , YEAR(`enrolment_date`) AS `year_enrolment` FROM `students` GROUP BY `year_enrolment`;
SELECT `exam_id` AS `appello_esame`,AVG(vote) AS `media_esame` FROM `exam_student` GROUP BY `exam_id`;



SELECT `students`.`degree_id`,`students`.`surname` AS `cognome`,`students`.`name`AS `nome`
FROM `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia' 
ORDER BY `cognome`,`nome`;


SELECT `departments`.`name`, `degrees`.`department_id`, `degrees`.`id`, `degrees`.`name` FROM `degrees` 
INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` 
WHERE `degrees`.`level` = "magistrale"
 AND `departments`.`name` = "Dipartimento di Neuroscienze";


SELECT `teachers`.*, `courses`.* 
FROM `teachers` 
INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id` 
INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id` 
WHERE `teachers`.`id` = 44;
