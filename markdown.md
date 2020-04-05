## Item G
```bash
cut -d ',' -f $(head -n 1 scorecard.csv | tr ',' '\n' | grep -n 'INSTNM'| cut -d ":" -f 1),$(head -n 1 scorecard.csv | tr ',' '\n' | grep -n 'UGDS$'| cut -d ":" -f 1) scorecard.csv | sort -t "," -k 2 -gr | head -n 10 | tr ',' '|' | sed -e 's/$/|/' | sed -e 's/^/|/'
```

|Institution| Size |
|-----------|-----|
|Western Governors University|88921|
|Southern New Hampshire University|80170|
|University of Phoenix-Arizona|70241|
|Ivy Tech Community College|59821|
|Lone Star College System|59074|
|University of Central Florida|58392|
|Houston Community College|57053|
|Grand Canyon University|53209|
|Texas A & M University-College Station|53194|
|Miami Dade College|49443|

## Item H
```bash
tail -n +2 scorecard.csv | cut -d ',' -f $(head -n 1 scorecard.csv | tr ',' '\n' | grep -n 'STABBR'| cut -d ":" -f 1) | sort | uniq -c|sort  -nr
