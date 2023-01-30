# odk-forms
Repository for various Open Data Kit xlsx and xml templates

## Fixing extra LF
Sometimes it seems quoted LF's end up in the CSV export. These can be removed using:
```
gawk -v RS='"' 'NR % 2 == 0 { gsub(/\n/, "") } { printf("%s%s", $0, RT) }' IN.csv > OUT.csv
```
