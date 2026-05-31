


```base
filters:
  and:
    - file.folder.startsWith("LYT/200 Calendar")
views:
  - type: table
    name: All
    sort:
      - property: file.name
        direction: ASC

```
