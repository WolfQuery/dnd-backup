```dataview
TABLE WITHOUT ID link(file.name) AS Object
WHERE contains(file.inlinks, this.file) AND contains(cssclasses, "json5e-object")
```