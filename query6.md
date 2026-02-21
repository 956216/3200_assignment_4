### Query 6
```SQL
SELECT DISTINCT a.Name
FROM artists a
JOIN albums al ON al.ArtistId = a.ArtistId
JOIN tracks t ON t.AlbumId = al.AlbumId
JOIN media_types mt ON mt.MediaTypeId = t.MediaTypeId
JOIN playlist_track pt ON pt.TrackId = t.TrackId
JOIN playlists p ON p.PlaylistId = pt.PlaylistId
WHERE p.Name IN ('Brazilian Music', 'Grunge')
  AND a.Name IS NOT NULL
  AND mt.Name IS NOT NULL
  AND mt.Name LIKE '%MPEG%';
```
This essentially selects names and joins together a bunch of tables through common IDs, and checks if the playlist names are within Brazilian/Grunge, ensuring the media type is MPEG.

### Results
```
Alice In Chains
Antônio Carlos Jobim
Caetano Veloso
Chico Buarque
Gilberto Gil
Elis Regina
Milton Nascimento
Jorge Ben
Gonzaguinha
Cássia Eller
Djavan
Eric Clapton
Nirvana
Pearl Jam
Soundgarden
Stone Temple Pilots
Tim Maia

```
