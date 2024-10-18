JSON from CSV :
```nu
open components-description.csv --raw | from csv | {"data": $in} | to json | save -f components-description.json
```

Readme :
```bash
j2 README.md.j2 components-description.json -o README.md
```
