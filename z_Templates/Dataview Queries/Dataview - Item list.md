```dataview
TABLE WITHOUT ID link(file.name) AS Item
WHERE contains(file.inlinks, this.file) AND contains(cssclasses, "json5e-item")
```
