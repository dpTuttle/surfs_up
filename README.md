# Python and SQLite Analysis for Weather Data on Oahu
### Overview of the Analysis: 
* The purpose of this analysis was to use data gathered from various weather stations around Oahu and review the high level statistics for temperature for the months of June and Decemeber across the period covered in the data set. 

### Results:
* As noted below, the average temperature for the month of June was 74.94 degrees:

![June_Data](https://github.com/dpTuttle/surfs_up/blob/main/Resources/jun_tobs.png)

* The June data also suggests that there is litlle variation between years or days in June given that each quartile is one standard deviation from another with no outliers. 

* For comparison, the average temperature for the month of December was 71.04 degrees: 

![Dec_Data](https://github.com/dpTuttle/surfs_up/blob/main/Resources/dec_tobs.png)

* The December data suggests that there is consistency across years and days in December as well (the data for each quartile is within one standard deviation of another), however, the minimum temperature is roughly 15 degrees lower than the average suggesting that there may have been some years where the temperature dropped lower than expected. We do not see the same gap in the June data. 

### Summary: 
* Overall, the data is evenly distributed for both months and across the year, we can infer that Oahu maintains a mild temperature between 71 degrees in the winter and 75 degrees in the summer. To further analyze this data, we can use two addtiional queries:
        
        The first, which would analyze the rainfall for a given month:
        results = session.query(Measurement.date, Measurement.prcp).filter(Measurement.date.like('%-06-%')).all()
        
        
        
        
        And another, that would gather the lowest temperature to determine what the average lowest temperature is for the island:
        results = session.query(Measurement.date, Measurement.tobs).filter(Measurement.tobs <= 60).all()
