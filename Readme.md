# Отсортируйте данные по полю заработная плата (salary) в порядке: убывания; возрастания для каждой группы
    SELECT *
    FROM staff
    ORDER BY post, salary DESC;
![Error](Query1.1.png)

    SELECT *
    FROM staff
    ORDER BY post, salary;
![Error](Query1.2.png)

# Выведите 5 максимальных заработных плат (saraly)

    SELECT salary
    FROM staff
    ORDER BY salary DESC
    LIMIT 5;
![Error](Query2.png)

# Посчитайте суммарную зарплату (salary) по каждой специальности (роst)

    SELECT 
	    post AS "Должность",
	    SUM(salary) AS "Суммарная ЗП"
    FROM staff
    GROUP BY post;
![Error](Query3.png)

# Найдите кол-во сотрудников с специальностью (post) «Рабочий» в возрасте от 24 до 49 лет включительно.

    SELECT COUNT(*) AS "Количество рабочих 24-49 лет"
    FROM staff
    WHERE post = "Рабочий" && age > 23 && age < 50;
![Error](Query4.png)

# Найдите количество специальностей

    SELECT COUNT(DISTINCT post) AS "Количество специальностей"
    FROM staff;
![Error](Query5.png)

# Выведите специальности, у которых средний возраст сотрудников меньше 35 лет

    SELECT post
    FROM staff
    GROUP BY post
    HAVING AVG(age) < 35;
![Error](Query6.png)