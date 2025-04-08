You need to group individual rows by time periods, Use resample to group rows by chunks of time, Our standard Titanic dataset does not contain a datetime column, so for this recipe we have generated a simple DataFrame
where each row is an individual sale. For each sale we know its date and time and its dollar amount (this data isn’t realistic because every sale takes place precisely 30 seconds apart and is an exact dollar amount,
but for the sake of simplicity let us pretend), The raw data looks like this, Notice that the date and time of each sale is the index of the DataFrame; this is because resample requires the index to be datetime-like
values, Using resample we can group the rows by a wide array of time periods (offsets) and then we can calculate some statistic on each time group, You might notice that in the two outputs the datetime index is a date
despite the fact that we are grouping by weeks and months, respectively. The reason is because by default resample returns the label of the right “edge” (the last label) of the time group. We can control this behavior using the label
parameter.
