```dataview
TABLE WITHOUT ID link(file.name) AS "Session Date", Status, players, OneLiner
from "2. Session Journals/Misty Forest"
where (type = "Session Journal")
SORT file.name DESC
```
