### Query 7
```SQL
SELECT COUNT(*)
FROM (
  SELECT a.ArtistId
  FROM artists a
  JOIN albums al ON al.ArtistId = a.ArtistId
  JOIN tracks t ON t.AlbumId = al.AlbumId
  JOIN media_types mt ON mt.MediaTypeId = t.MediaTypeId
  WHERE a.Name IS NOT NULL
    AND mt.Name IS NOT NULL
    AND mt.Name LIKE '%MPEG%'
  GROUP BY a.ArtistId
  HAVING COUNT(t.TrackId) >= 10
);
```
This query takes the count of artist Ids where the media type of a track contains MPEG, and they have over or equal to 10 of those tracks.

### RESULTS
```
114
```
