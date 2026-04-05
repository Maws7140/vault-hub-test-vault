# Project Dashboard

## Active Projects

```dataview
TABLE status AS "Status", due AS "Due Date", priority AS "Priority"
FROM "Projects"
WHERE status != "completed"
SORT priority ASC
```

## Tasks Due This Week

```tasks
not done
due before next week
sort by due
group by filename
```

## Recently Modified

```dataview
TABLE file.mtime AS "Modified"
FROM ""
WHERE file.mtime >= date(today) - dur(7 days)
SORT file.mtime DESC
LIMIT 10
```
