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

**How to aggregate hourly data of an xts object?**
```
d_xts_hourly = period.apply(d_xts, endpoints(d_xts, "hours"), sum)
```

**How to convert an xts object to dataframe so that dates are stored in a separate column?**
```
df = data.frame(date=index(x), coredata(x))
```

**How to extract hour from a POSIXct object?**
```
hour = as.POSIXlt(posixct)$hour
```
