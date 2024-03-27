# SQL_Assignment_12

## Sorgu Senaryoları

* film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?

```bash
SELECT COUNT(*) AS film_sayisi
FROM film
WHERE length > (SELECT AVG(length) FROM film);
```

* film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

```bash
SELECT COUNT(*) AS film_sayisi
FROM film
WHERE rental_rate = (SELECT MAX(rental_rate) FROM film);
```

* film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.


```bash
SELECT film_id, title, rental_rate, replacement_cost
FROM film
ORDER BY rental_rate ASC, replacement_cost ASC;
```

* payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

```bash
SELECT customer_id, COUNT(*) AS alisveris_sayisi
FROM payment
GROUP BY customer_id
ORDER BY alisveris_sayisi DESC;
```