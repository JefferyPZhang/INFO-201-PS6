# INFO 201 Problem Set: Merge and Reshape Data
November 23, 2023

1 How is CO2 related to global temperature?
This tasks asks you to make a plot where you show how CO2 concentration is related to global
temperature anomaly.
1.1 Scripps CO2 data
First, let’s look at Scripps CO2 data.
1. Load the dataset. Ensure it is good.
Below, you only need variables year, month, and co2. You can keep only these columns and
drop everything else.
2. What does a line in this dataset represent?
3. How are missing values coded in this dataset?
4. Which time period does the dataset represent?
5. Make a plot where you show how the CO2 concentration in atmosphere has changed over
years.
Hint: the result should look like on the Scripps CO2 program’s page.
6. Comment the graph. How has CO2 level changed through the last 60 years?
1
1.2 HadCRUT temperature data
Next, take a look at HadCRUT temperature data. This is considered to be one of the best datasets
for global surface temperature.
1. Load data and ensure it looks good.
Below, you only need year and temperature anomaly, you can as well drop the other columns
now (and rename the ones you need to something better).
2. What does a line in this dataset represent?
3. Which time period does the dataset represent?
4. When you encounter political discussion related to future global temperature levels, you hear
values like 1.5C and 2C above pre-industrial temperature. However, we have a problem–
HadCRUT anomaly is not above the pre-industrial temperature, but above 1961-1990 average.
Compute the pre-industrial (year 1900 and before) average, and create a new column–temperature
anomaly over the pre-industrial average (pre-industrial baseline).
Show how big is the pre-industrial average, when compared to the 1961-1990 average.
5. Make a plot where you show how has global surface temperature changed through time. Use
the anomaly w.r.t. the pre-industrial baseline.
6. Comment the plot. How has the global temperature evolved throught last 170 years?
7. Has been trending up since 1920 or so, pretty consistent trend since 1960.
1.3 How is global temperature related to CO2 levels?
How it is time to put the two previous datasets together. The final result here should be a plot:
how is global temperature related to CO2 levels in atmosphere.
1. What kind of variables you can imagine to use to merge CO2 data with global temperature
data–what might be the merge key?
2. But we have a problem. CO2 data is monthly but temperature data yearly only. How might
you still be able to merge these two datasets?
3. Merge these two datasets. What kind of merge–left inner join/right join/left join/... you want
to use? Explain!
4. Make a plot in CO2-temperature anomaly axis (see below).
(a) Use the temperature anomaly wrt the pre-industrial average.
(b) Mark years with dots or other suitable symbols.
(c) Mark decades with colors. Use some sort of heat-describing colors.
(d) Put the trend line on the figure, use a suitable color to mark it.
(e) add a horizontal line at 1.5C anomaly.
2
(f) Ensure that labels are clear enough.
The plot should look something along this, but using colors, not just b/w:0.0
0.5
1.0
1.5
325 350 375 400 425
CO2 concentration (ppm)
Temperature anomaly
(w.r.t 1850−1900 average), °C decade
1950
1960
1970
1980
1990
2000
2010
2020
2 Global surface temperature versus lower troposphere tempera-
ture
Here we compare global surface temperature recordings (HadCRUT) with satellite measurements
(UAH lower troposphere). Satellites do not measure temperature directly on the surface, but in
“lower troposphere”, in the air column above us. We use UAH lower troposphere data UAH-lower-
troposphere-wide.csv.bz2.
1. Load data and ensure it looks good. Below, you only need variables year, month and globe,
so you can select just those.
2. As we want to compare monthly UAH data with yearly HadCRUT measures, you need to
compute yearly UAH averages.
3. Now merge HadCRUT and UAH data. Show that the result is good.
Below, we only need year and the one anomaly from each dataset, so if you have more variables,
you can drop them now.
4. Is this dataset in a wide or long form?
5. Reshape it into long form. The variables should be something like “year”, “anomaly” and
“type”, and the later should be type of anomaly (surface/lower troposphere)
It might look something like this:
3
## # A tibble: 6 x 3
## year type anomaly
## <dbl> <chr> <dbl>
## 1 1978 surface 0.362
## 2 1978 lower troposphere -0.48
## 3 1979 surface 0.447
## 4 1979 lower troposphere -0.348
## 5 1980 surface 0.553
## 6 1980 lower troposphere -0.179
6. Make a plot where you show how temperature anomaly changes over years. Mark both types
with a different color, and add trend lines for each type. Which temperature–surface of lower
troposhphere–is growing faster?
Note: the trend lines are at a different level, unless you re-calibrate the anomalies. You
cannot use pre-industrial average for lower troposphere, because we do not have satellite
measurements from 19th century...
Finally tell us how many hours did you spend on this PS.
