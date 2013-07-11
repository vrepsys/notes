## Notes on R

**How do you subset an xts object to include only one of a few weekdays?**

```R
weekdays = x[.indexwday(x) %in% 1:5]
```
