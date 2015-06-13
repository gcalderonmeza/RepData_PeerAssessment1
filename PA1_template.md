# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data


```r
unzip("activity.zip", overwrite = TRUE, exdir = ".")
activityData <- read.csv("activity.csv")
##activityData$date <- strptime(as.character(activityData$date), "%Y-%m-%d")
```

## What is mean total number of steps taken per day?


```r
# Calculate the total number of steps taken per day (ignoring NAs)
aggregatedData <- aggregate(steps~date, data=activityData, FUN="sum", na.action = na.omit)

# Hisorgram of the total number of steps taken per day
#png("plot1.png", width = 480, height = 480)
with(aggregatedData, hist(steps, main = "Number of steps per day", xlab = "Steps per day", col="red"))
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

```r
#dev.off()

# Report the mean and median of the total number of steps taken per day
mean(aggregatedData$steps)
```

```
## [1] 10766.19
```

```r
median(aggregatedData$steps)
```

```
## [1] 10765
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
