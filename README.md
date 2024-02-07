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
