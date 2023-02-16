# Algobulls-assignment

Project: Design a simple Algorithmic Trading Strategy
Description: You need to code a simple trading strategy in a Jupyter Notebook as per the
given requirements:
1. Define a Class ScriptData which can fetch US Stock data using Alpha Vantage.
[Use this link to get your FREE API Key].
The class should implement the following methods:
a. fetch_intraday_data: (method arguments: script)
Fetches intraday data for given “script” (Example for script: “GOOGL”,
“AAPL”) and stores as it is.
b. convert_intraday_data: (method arguments: script)
Converts fetched intraday data (in point a.) as a pandas DataFrame
(hereafter referred as “df”) with the following columns:
i. timestamp (data type: pandas.Timestamp)
ii. open (data type: float)
iii. high (data type: float)
iv. low(data type: float)
v. close (data type: float)
vi. volume (data type: int)
c. Additional methods for overloading the following operations:
i. getitem
ii. setitem
iii. contains
Sample code showing how the above class will be used:
(The output data may differ for you based on which date you run this code, but the format should be the same)
(The output data may differ for you based on which date you run this code, but the format should be the same)
2. Define a function called indicator1. It should take “df” and ‘timeperiod’ (integer) as
inputs and give another pandas DataFrame as an output with two columns:
a. timestamp: Same as ‘timestamp’ column in ‘df’
b. indicator: Moving Average of the ‘close’ column in ‘df’. The number of
elements to be taken for a moving average is defined by ‘timeperiod’. For
example, if ‘timeperiod’ is 5, then each row in this column will be an average
of total 5 previous values (including current value) of the ‘close’ column.
Some sample code has been given below which shows how the above function will be used:
3. Define a class Strategy, which can do the following, given a script name:
a. Fetch intraday historical day (‘df’) using ScriptData class.
We’ll refer to the ‘close’ column of ‘df’ as close_data.
b. Compute indicator data on ‘close’ of ‘df’ using indicator1 function.
We’ll refer to the ‘indicator’ column of this data as indicator_data.
c. Generate a pandas DataFrame called ‘signals’ with 2 columns:
i. ‘timestamp’: Same as ‘timestamp’ column in ‘df’
ii. ‘signal’: This column can have the following values:
 BUY (When: If indicator_data cuts close_data upwards)
 SELL (When: If indicator_data cuts close_data downwards)
 NO_SIGNAL (When: If indicator_data and close_data don’t cut
each other)
Example of ‘Cut Upwards’, ‘Cut Downwards’, ‘Do not cut each
other’:
As an example, for the below graph, if the RED line is
close_data and GREY line is indicator_data, then:
i. The BLUE points represent the instances when
indicator_data has cut close_data ‘downwards’
ii. The PINK points represent the instances when
indicator_data has cut close_data ‘upwards
iv. The YELLOW points represent when indicator_data
and close_data don’t cut each other.
So, there will be SELL signal for BLUE timestamps, ‘BUY’
signal for PINK timestamp and ‘NO_SIGNAL’ for yellow
timestamps.
d. Print the ‘signals’ DataFrame with only those rows where the signal is either
‘BUY’ or ‘SELL’.
Sample code showing how the above class will be used:
4. [OPTIONAL] Plot a candlestick chart of ‘df and ‘indicator’. You can use
‘pyalgotrading’ to do so. The chart will look like this
