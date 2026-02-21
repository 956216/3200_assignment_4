### AI Disclaimer
- I asked Gemini 3 Pro (Web): "Please explain sql window functions to me. Give me a couple simple examples"
- I was unfamiliar with the term.
- Note: it had some leftover context from query 8. It didn't know the layout of the database, but I mentioned playlists and tracks were involved.
- Response (cut down):
```SQL
SELECT 
    column_name,
    FUNCTION() OVER (PARTITION BY group_col ORDER BY sort_col)
FROM Table;

SELECT 
    sale_date, 
    amount,
    SUM(amount) OVER (ORDER BY sale_date) AS running_total
FROM Sales;

SELECT 
    playlist_id,
    track_name,
    duration,
    RANK() OVER (PARTITION BY playlist_id ORDER BY duration DESC) AS track_rank
FROM Tracks;

SELECT 
    playlist_name,
    track_name,
    ROW_NUMBER() OVER (
        PARTITION BY playlist_name 
        ORDER BY track_name ASC
    ) AS play_order
FROM Tracks;
```

### QUERY 9
```SQL
SELECT PlaylistId, PlaylistName, TrackName, Milliseconds
FROM (
  SELECT p.PlaylistId, p.Name AS PlaylistName, t.Name AS TrackName, t.Milliseconds,
         ROW_NUMBER() OVER (
           PARTITION BY p.PlaylistId
           ORDER BY t.Milliseconds DESC
         ) AS rn
  FROM playlists p
  JOIN playlist_track pt ON pt.PlaylistId = p.PlaylistId
  JOIN tracks t ON t.TrackId = pt.TrackId
) x
WHERE rn = 1;
```

This is my creative addition. It finds the longest track on each playlist. The tables it joins: playlists, playlist_track, tracks. It uses a window function to rank tracks (per playlist ID) by length, descending. It then retrieves the first rank of each playlist Id.

### RESULTS
```
1|Music|Dazed And Confused|1612329
3|TV Shows|Occupation / Precipice|5286953
5|90’s Music|Dazed And Confused|1116734
8|Music|Dazed And Confused|1612329
9|Music Videos|Band Members Discuss Tracks from "Revelations"|294294
10|TV Shows|Occupation / Precipice|5286953
11|Brazilian Music|Vai Passar|369763
12|Classical|Adagio for Strings from the String Quartet, Op. 11|596519
13|Classical 101 - Deep Cuts|Symphony No. 3 Op. 36 for Orchestra and Soprano "Symfonia Piesni Zalosnych" \ Lento E Largo - Tranquillissimo|567494
14|Classical 101 - Next Steps|Symphonie Fantastique, Op. 14: V. Songe d'une nuit du sabbat|561967
15|Classical 101 - The Basics|Adagio for Strings from the String Quartet, Op. 11|596519
16|Grunge|Alive|341080
17|Heavy Metal Classic|Master Of Puppets|515239
18|On-The-Go 1|Now's The Time|197459
```
