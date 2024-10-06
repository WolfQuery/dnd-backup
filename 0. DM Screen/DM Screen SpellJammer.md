---
banner: "![[Spelljammer_banner.jpg]]"
banner_y: 0.38
banner_lock: true
text: DM Screen
---
| ![[Sky Chart.jpg\|hsmall+wsmall+center]] | ![[Imagename2.png\|hsmall+wsmall+center]] | ![[Imagename3.png\|hsmall+wsmall+center]] | ![[Imagename4.png\|hsmall+wsmall+center]] |     |
| ------------------ | ----------------------------------------- | ----------------------------------------- | ----------------------------------------- | --- |
| [[Map]]      | [[Sess]]                             | [[Notename3]]                             | [[Notename4\|Rename Note Name]]           |     |

# DM screen
## Players
```dataview
table Player, Class, Race, level, Role
from "1. Players/Spelljammer"
where (Role = "Player") 
where (Status = "Active") 
```

### Known languages by party
```dataviewjs
dv.list(dv.pages()
		.where(p => p.Status && p.Status.includes("Active") && p.Role && p.Role.includes("Player"))
		.PlayerKnownLanguages.distinct())
```

## Players Combat info
```dataview
TABLE WITHOUT ID link(file.name) AS "Character Name", Player, hp, ac, modifier, pasperc AS "Passive Perception (WIS)", speed AS "Speed"
WHERE (Role = "Player")
WHERE (Status = "Active")
```



## Session Journals
```dataview
TABLE WITHOUT ID link(file.name) AS "Session Date", Status, players, OneLiner
from "z_published files/2. Session Journals/Spelljammer"
where (type = "Session Journal")
SORT file.name DESC
```

## Recently Modified
### NPCs
```dataview  
TABLE WITHOUT ID link(file.name) AS "NPC Name", Gender, Race, Age, Location, AssociatedGroup  
FROM "2. Mechanics/Non-Player Characters"
WHERE (NoteIcon = "npc") 
SORT file.mtime DESC
LIMIT 10
```
### Locations
```dataview  
TABLE WITHOUT ID link(file.name) AS "Location Name", type, Government, Community-Size, size, population  
FROM "1. World"
WHERE (NoteIcon = "Settlement")  
SORT file.mtime DESC
LIMIT 10
```
