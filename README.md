SELECT \* FROM students
WHERE YEAR(date_of_birth) = 1990;

SELECT \* FROM courses
WHERE cfu > 10;

SELECT \* FROM students
WHERE Year(date_of_birth) < '1995-04-10';

SELECT \* FROM courses
WHERE period = 'I semestre' AND year = 1;

SELECT \* FROM exams
WHERE date = '2020-06-20' AND hour > '14:00:00';

SELECT \* FROM degrees
WHERE level = 'magistrale';

SELECT id FROM departments;

SELECT \* FROM teachers
WHERE phone IS NULL;
