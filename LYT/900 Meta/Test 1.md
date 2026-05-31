

```dataview
TABLE
item.title as Name,
item.url as URL,
item.category as Category,
item.rating as Rating
FLATTEN file.lists as item
WHERE item.url
```

