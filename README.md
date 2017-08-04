# Stock-Market-Prediction
### Project Overview###

We are analyzing daily stock market data to determine if there is a significant difference between signal dates (day after an earnings report) and other dates. Read the guidelines below carefully before you start contributing.

1) First phase is to determine if there is any trend on signal dates that doesn't appear on other dates. Are oscillation patterns on signal dates special? For this phase, we can focus on one ticker.

If the answer is yes, we move on to next phase.

2) Second phase is to check for (partial) similarities in their oscillation patterns between different tickers on signal dates.

If we find common features, we will then create a predictive model incorporating these features.


### Files added ###

manifest_sample.csv, signal date data, ref date data, other date data

***A) manifest_sample.csv:***
  contains data summary for a single ticker. 

Fields:

signaldate: date of the earnings event

AMC_BMO: AMC indicates the event occured after market close on signaldate, BMO indicates before market open on signaldate

refdate: the date of the first market close PRIOR to the event. So if the signal is AMC, it is the same date as signaldate.

refrv: annualized 22 day realized volatility prior to event. defined as standard deviation of 22 days of daily returns. 

ref22adv: 22 day average daily volume prior to event

refvolume: volume traded on reference date

refopen: opening price on reference date

refhi: intraday high price on reference date

reflo: intraday low price on reference date

refclose: closing price on reference date

firstdate: date of first market closing AFTER the event. so for BMO events, it is the same as signaldate

firstvolume: volume traded on first date after event

firstopen: opening price on first date after event

firsthi: highest traded price on first date after event

firstlo: lowest traded price on first date after event

firstclose: first closing price after event

datelen: number of dates there is data for that ticker

dates: a list of all dates there is data for that ticker

***B) data files:***

signal date and reference date data are marked with _signal and _ref file names.

  each file contains data for the same ticker for the specified date ("dates" field in manifest file). The important fields here are recv.time and px. But you're welcome to play with any other field as well.

Fields:

recv.time : timestamp of when i received the trade (converted into POSIX format)

px : the price the trade occurred at

shares : running shares traded that day so far

exchange : in open market hours, a letter indicating what exchange the trade occurred on

bid : the bid price in the market at the time of the trade. this is the best price one could sell at

bidsz : the amount of shares you could sell shares at the bid price at the time of the trade

ask : the ask price in the market at the time of the trade. this is the best price one could buy at

asksz : the number of shares you could buy at the ask price at the time of the trade
