### Query 5
```SQL
SELECT DISTINCT
  artists.Name
FROM artists
JOIN albums
  ON albums.ArtistId = artists.ArtistId
WHERE albums.Title LIKE '%symphony%';
```

### Results
```
Sergei Prokofiev & Yuri Temirkanov
Otto Klemperer & Philharmonia Orchestra
Adrian Leaper & Doreen de Feis
Berliner Philharmoniker & Herbert Von Karajan
```
