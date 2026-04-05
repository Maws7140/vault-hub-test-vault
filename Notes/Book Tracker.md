# Book Tracker

## Currently Reading

```dataview
TABLE author AS "Author", rating AS "Rating", started AS "Started"
FROM "Books"
WHERE status = "reading"
SORT started DESC
```

## Want to Read

```dataview
TABLE author AS "Author", genre AS "Genre"
FROM "Books"
WHERE status = "want-to-read"
SORT file.ctime DESC
```

## Finished This Year

```dataview
TABLE author AS "Author", rating AS "Rating", finished AS "Finished"
FROM "Books"
WHERE status = "finished" AND finished >= date(2026-01-01)
SORT finished DESC
```

## Stats

Total books read: `= length(filter(file.lists, (x) => x.status = "finished"))`
