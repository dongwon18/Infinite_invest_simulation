# Infinite Invest Backtest Simulation
## Purpose
- using previous data, simulate infinite invest method

## Variable
- invest start date
  - format: yyyy-mm-dd
  - no format checking → if not follow the format, error could occur 
  - if the input date is not trading day(ex holiday), find next trading date
- invest end date
  - format: yyyy-mm-dd
  - no format checking → if not follow the format, error could occur
  - no limit for the last date → if enter the date not in data range, error could occur 
- the number of date for one iteration
  - usually, the infinit invest method uses 40
- simple interest vs compound interest
  - simple interest(0)
    - if earn money, do not use it for the next iteration
    - for all iteration, invest given investment amount
  - compound interest(1)
    - if eary or lose money, use it for the next iteration
    - for each iteraton, investment amount is the result of the previous iteration
- investment amount
  - should be large enough to buy more than one stock for each day
  - ex 10,000
- file to be used for simulation
  - format
    - (1,1): code
    - (2,1): date, (2, 6): closing price 
    - other columns are not important
  - utf-8 csv format 

# Algorithm
- investment for a day is investment amount / no. of date for one iteration
- the number of stocks for a day to buy: investment amount for a day // closing price of the date
- if the moeny is not enough to buy a stock, do not buy
- if yield is equal or more than 10%, sell all stocks for the iteration and finish the iteration 
- if yield has not been equal or more than 10% until the iteration overs, finish the iteration
- after finishing the iteration, save the result at output file
- start new iteration until it reaches givn end date

# Prerequisite
- should follow the format for variables
- data file should be placed in the same forlder with the code

# Development environment
- Google Colaboratory

# Result
- get output file (name: *code*_infinite_invest.csv)

# Note
- the code do not have any format checking
