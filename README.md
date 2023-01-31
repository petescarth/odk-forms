# odk-forms
Repository for various Open Data Kit xlsx and xml templates

## Fixing extra LF
Sometimes it seems quoted LF's end up in the CSV export. These can be removed using:
```
gawk -v RS='"' 'NR % 2 == 0 { gsub(/\n/, "") } { printf("%s%s", $0, RT) }' IN.csv > OUT.csv
```
## Projecting points with distance and bearing in QGIS "Geometry By Expression" tool
```
 project (($geometry),
 if("site-distance" is null,0,"site-distance"),
 radians ( if("site-bearing" is null,0,"site-bearing") )) 
 ```
 
