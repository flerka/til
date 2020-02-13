# Add computed column to csv + regex search in another column.

Example
Id,Url,Name
1,test/11112/new-game,New Game

Will be transformed in
Id,Url,Name,UrlId
1,test/11112/new-game,New Game,11112

```
awk -F"," 'FNR==1{a="UrlId"} FNR>1{a=$1} {match(a, /\/([[:digit:]]+)\//)} {print $0","substr(a, RSTART+1, RLENGTH-2)}' old.csv > new.csv
```
