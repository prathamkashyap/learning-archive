# Linux Text Processing

## Context

Text commands turn logs and command output into something searchable. I use these before opening huge files manually.

## grep

```bash
grep "error" app.log
grep -i "error" app.log
grep -R "TODO" .
grep -n "function" file.js
```

## awk

```bash
awk '{print $1}' access.log
awk -F, '{print $2}' data.csv
awk '$3 > 100 {print $1, $3}' file.txt
```

## sed

```bash
sed 's/old/new/' file.txt
sed 's/old/new/g' file.txt
sed -n '10,20p' file.txt
```

## Archives

```bash
tar -czf archive.tar.gz folder
tar -xzf archive.tar.gz
zip -r archive.zip folder
unzip archive.zip
```

## Common Mistakes

- Forgetting quotes around patterns with spaces.
- Using `sed -i` before testing the replacement.
- Treating CSV as simple text when fields can contain commas.
- Searching generated dependency folders by accident.

## Quick Reference

| Need | Command |
| --- | --- |
| Search recursively | `grep -R "text" .` |
| Case-insensitive search | `grep -i "text" file` |
| Print column | `awk '{print $1}' file` |
| Replace text | `sed 's/old/new/g' file` |
| Create tar.gz | `tar -czf archive.tar.gz folder` |
