# 🎵 Music Store SQL Analytics Project

This project explores a fictional music store database using PostgreSQL and SQL to answer key business questions related to customer behavior, artist performance, and genre insights.

## 📁 Dataset Overview

The database contains the following tables:
- `customer`
- `invoice`
- `invoice_line`
- `track`
- `album`
- `artist`
- `genre`
- `employee`

## 🎯 Objectives

- Identify the top-spending customers
- Analyze revenue by country and city
- Determine the most popular music genres and artists
- Explore song duration patterns
- Use SQL to answer real-world business questions

## 🛠️ Tools & Skills Used

- **PostgreSQL**
- **SQL** (`JOIN`, `GROUP BY`, `HAVING`, subqueries, window functions)
- **Data Visualization** (Canva)

## 🔍 Key Queries

1. Best customer and city by total revenue
2. Countries with the most invoices
3. Top 10 Rock artists by number of songs
4. Tracks longer than average length
5. Rock music listener profiling by email

## 📊 Sample Query

```sql
SELECT artist.name, COUNT(track.track_id) AS number_of_songs
FROM artist
JOIN album ON artist.artist_id = album.artist_id
JOIN track ON album.album_id = track.album_id
JOIN genre ON track.genre_id = genre.genre_id
WHERE genre.name LIKE 'Rock'
GROUP BY artist.name
ORDER BY number_of_songs DESC
LIMIT 10;
