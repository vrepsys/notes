## Notes on R

**How to read data from a csv file**
```
df = read.csv('data.csv')
```


**How do you subset an xts object to include only one of a few weekdays?**
```
weekdays = x[.indexwday(x) %in% 1:5]
```

**How to convert date string to POSIXct and add as a column to a data frame?**
```
df$dtime <- as.POSIXct(strptime(df[, 3], "%Y-%m-%d %H:%M:%S"), "GMT")
```

**How to order a data frame?**

By column index:
```
dd[ order(-df[,4], df[,1]), ]
```
By column name:
```
df[with(dd, order(-z, b)), ]
```
