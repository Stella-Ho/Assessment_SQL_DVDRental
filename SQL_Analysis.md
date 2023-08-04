# DVD Rental SQL Analysis
The below 10 queries generated data for DVD rental analysis. It also attached the csv result of each of the query in the sepeate file.

**1.	SELECT and WHERE and LIKE**
```
SELECT actor_id, first_name, last_name FROM actor WHERE last_name LIKE 'B%'
```
This query retrieves the actor id, first and last names of actors whose last name is start with “B”. It helps to list out actors who are the same last name which begin with Letter “B”.

**2.	DISTINCT and OPERATOR**
```
SELECT DISTINCT customer_id FROM payment WHERE amount <.99 ORDER BY customer_id Asc;
```
This query listed out customer id by ascending order, if each payment is less than 0.99.

**3.	BETWEEN and NOT**
```
SELECT film_id, rental_duration FROM film WHERE rental_duration NOT BETWEEN 5 AND 7;
```
This query is to find out film id which the rental duration is not between 5 to 7, so it finds that the result is 3 and 4.

**4.	SUM and HAVING**
```
SELECT customer_id, SUM(p.amount) AS total_amount
FROM payment p
GROUP BY customer_id
HAVING SUM(p.amount) > 100
ORDER BY total_amount ASC;
```
This query showed that customer id by ascending order, if the payment total amount is more than 100.

**5.	JOIN and IN**
```
SELECT c.category_id, c.name, fc.film_id, f.title
FROM category c
JOIN film_category fc ON c.category_id = fc.category_id
JOIN film f ON f.film_id = fc.film_id
WHERE c.name IN ('Action', 'Family')
ORDER BY category_id ASC;
```
This query filtered out the film category include “Action” and “Family” and also JOIN the table which can see the film id and film title.

**6.	COUNT and LIMIT**
```
SELECT fa.actor_id, COUNT(f.film_id) as film_count, a.first_name
FROM film_actor fa
INNER JOIN film f ON f.film_id = fa.film_id
INNER JOIN actor a ON a.actor_id = fa.actor_id
GROUP BY fa.actor_id, a.first_name
ORDER BY film_count DESC
Limit 10;
```
This query shows the actor produced number of film and only filtered out top 10 of actor id and actor name.

**7.	MAX, MIN**
```
SELECT fc.category_id, c.name, MAX(length) as Max_length, MIN(length) as Min_length
FROM film f
JOIN film_category fc ON fc.film_id = f.film_id
JOIN category c ON fc.category_id = c.category_id
GROUP BY fc.category_id, c.name
ORDER BY category_id ASC;
```
This query is listed out the maximum and minimum length of the film by ascending order with category id and category name. 

**8.	RANK and WINDOW FUNCTION**
```
SELECT customer_id, amount, 
RANK() OVER (ORDER BY amount) as rank
FROM payment
WHERE amount > 10;
```
This query is ranked the payment amount more than 10, there are only two results is 10.99 and 11.99.

**9.	CASE and ORDER BY**
```
SELECT customer_id, active,
	CASE WHEN active='0' THEN 'INACTIVE'
		ELSE 'ACTIVE'
	END
FROM customer
ORDER BY customer_id;
```
This query can check customer status more easily as “ACTIVE” and “INACTIVE” instead of seeing the values as “0” or “1”. 

**10.	STRING_AGG**
```
SELECT co.country_id, co.country, STRING_AGG(email,';') email_list
FROM customer cu
JOIN address a ON a.address_id = cu.address_id
JOIN city ci ON ci.city_id = a.city_id
JOIN country co ON ci.country_id = co.country_id
GROUP BY co.country_id, co.country
ORDER BY co.country_id ASC;
```
This query is to consolidate all the customers email address and listed out by country.
