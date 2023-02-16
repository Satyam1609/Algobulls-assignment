# Algobulls-assignment

Project: Design a simple Algorithmic Trading Strategy
Description: You need to code a simple trading strategy in a Jupyter Notebook as per the
given requirements:

1. Define a Class ScriptData which can fetch US Stock data using Alpha Vantage. The class should implement the following methods:
    - fetch_intraday_data: (method arguments: script) Fetches intraday data for given “script” (Example for script: “GOOGL”, “AAPL”) and stores as it is.
    - convert_intraday_data: (method arguments: script) Converts fetched intraday data (in point a.) as a pandas DataFrame (hereafter referred as “df”) with the following columns:
        1. timestamp (data type: pandas.Timestamp)
        2. open (data type: float)
        3. high (data type: float)
        4. low(data type: float)
        5. close (data type: float)
        6. volume (data type: int)
    - Additional methods for overloading the following operations:
        1. getitem
        2. setitem
        3. contains

2. Define a function called indicator1. It should take “df” and ‘timeperiod’ (integer) as inputs and give another pandas DataFrame as an output with two columns:
    - timestamp: Same as ‘timestamp’ column in ‘df’
    - indicator: Moving Average of the ‘close’ column in ‘df’. The number of elements to be taken for a moving average is defined by ‘timeperiod’. For example, if ‘timeperiod’ is 5, then each row in this column will be an average of total 5 previous values (including current value) of the ‘close’ column.

3. Define a class Strategy, which can do the following, given a script name:
    - Fetch intraday historical day (‘df’) using ScriptData class. We’ll refer to the ‘close’ column of ‘df’ as close_data.
    - Compute indicator data on ‘close’ of ‘df’ using indicator1 function. We’ll refer to the ‘indicator’ column of this data as indicator_data.
    - Generate a pandas DataFrame called ‘signals’ with 2 columns:
        1. ‘timestamp’: Same as ‘timestamp’ column in ‘df’
        2. ‘signal’: This column can have the following values:
            BUY (When: If indicator_data cuts close_data upwards)
            SELL (When: If indicator_data cuts close_data downwards)
            NO_SIGNAL (When: If indicator_data and close_data don’t cut each other)

    - Print the ‘signals’ DataFrame with only those rows where the signal is either ‘BUY’ or ‘SELL’.

4. [OPTIONAL] Plot a candlestick chart of ‘df and ‘indicator’. You can use ‘pyalgotrading’ to do so. The chart will look like this
