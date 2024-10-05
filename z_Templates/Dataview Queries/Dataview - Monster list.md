
```dataview
TABLE WITHOUT ID link(file.name) AS Monster
WHERE contains(file.inlinks, this.file) AND contains(cssclasses, "json5e-monster")
```
