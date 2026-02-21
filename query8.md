### AI DISCLAIMER
- I asked Gemini 3 Pro (web): "
- I asked this because I was unfamiliar with dealing with numbers and totals.
- Answer:
```SQL
SELECT 
    p.playlist_id, 
    p.name, 
    SUM(t.duration_seconds) AS total_duration
FROM Playlists p
JOIN Tracks t ON p.playlist_id = t.playlist_id
GROUP BY p.playlist_id, p.name
HAVING SUM(t.duration_seconds) > 3600; -- Filters for playlists longer than 1 hour
```

### Query 8
```SQL
SELECT p.PlaylistId, p.Name, ROUND(SUM(t.Milliseconds) / 3600000.0, 2) AS Hours
FROM playlists p
JOIN playlist_track pt ON pt.PlaylistId = p.PlaylistId
JOIN tracks t ON t.TrackId = pt.TrackId
WHERE p.Name IS NOT NULL
GROUP BY p.PlaylistId, p.Name
HAVING SUM(t.Milliseconds) > 7200000;
```
This query selects playlist ID and names, as well as their hours of playlists (without null names) where the sum of tracks is greater than two hours.

### Result
```
1|Music|243.8
3|TV Shows|139.19
5|90’s Music|110.75
8|Music|243.8
10|TV Shows|139.19
11|Brazilian Music|2.64
12|Classical|6.05
14|Classical 101 - Next Steps|2.1
15|Classical 101 - The Basics|2.07
17|Heavy Metal Classic|2.28

```
