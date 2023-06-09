# Manipulating-Time-Series-Data
 Time series data are data that are indexed by a sequence of dates or times. We'll practice how to use methods built into Pandas to work with this index. We'll also practice how resample time series to change the frequency. 


## Date & Time Series functionality

- data types for date & time information 
  - Objects for points in time and periods
  - Attributes & method reflects time-related details

- Sequences of dates & periods 
  - Series or DataFrame columns
  - Index: convert object into Time Series 

- Many Series/ DataFrame methods rely on time information in the index to provide time-series functionality

## Time series transformation 

- Basic time series transformation include:
  - Parsing string dates and convert to `datetime64`
  - Selecting & slicing for specific subperiods
  - Setting & changing `DateTimeIndex` frequency: Upsampling vs Downsampling 
 
## Basic time series calculations

- Typical Time Series manipulations includes:
  - Shift or lag values back or forward back in time
  - Get the difference in value for a given time period
  - Compute the percent change over any number of periods
- `pandas` built-in methods rely on `pf.DateTimeIndex`

## Comparing stock performance 

- Stock price series: hard to compare at different levels
- Simple solution: normalize price series to start at 100
- Divide all prices by first in series, multiply by 100
  - Same starting point
  - All prices relative to starting point 
  - Difference to starting point in percentage points

## Changing the frequency: resampling

- `DateTimeIndex`: set & change freq using `.asfreq()`
- But frequency conversion affects the data
  - Upsampling: fill or interpolate missing data
  - Downsampling: aggregate existing data
- `pandas` API:
  - `.asfreq()`, `.reindex()`
  - `.resample()` + transformation method

## Frequency conversion & transformation methods

- `.resample()`: similar to `.groupby()`
- Groups data within resampling period and applies one or several methods to each group
- New date determined by offset - start, end, etc
- Upsampling: fill from existing or interpolate values
- Downsampling: apply aggregation to existing data

## Downsampling & aggregation methods 

- Downsampling: hour to day, day to month, etc
- How to represent the existing values at the new date?
  - Mean, median, last value?

## Windows functions in pandas 

- Windows identify sub periods of your time series 
- Calculate metrics for sub periods inside the window 
- Create a new time series of metrics 
- Two types of windows:
  - Rolling: same size, sliding 
  - Expanding: contain all prior values

## Expanding windows in pandas

- From rolling to expanding windows 
- Calculate metrics for periods up to current data 
- New time series reflects all historical values
- Useful for running rate of return, running min/ max
- Two options with pandas:
  - `.expanding()` - just like `.rolling()`
  - `.cusum()`, `.cumprod()`, `cummin()`/`max()` 

## Random walks & simulations

- Daily stock returns are hard to predict
- Models often assume they are random in nature
- Numpy allows you to generate random numbers 
- From random returns to prices: `.cumprod()`
- Two examples:
  - Generate random returns 
  - Randomly selected actual SP500 returns


