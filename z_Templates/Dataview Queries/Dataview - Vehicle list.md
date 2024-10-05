```dataview
TABLE WITHOUT ID link(file.name) AS Vehicle
WHERE contains(file.inlinks, this.file) AND contains(cssclasses, "json5e-vehicle")
```