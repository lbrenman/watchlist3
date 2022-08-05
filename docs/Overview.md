---
stoplight-id: p64baz5fig4ns
---

# Overview

This is a stock watchlist API which can be used to display a list of stocks that you would like to "watch" along with the latest price and the change from the market open price as illustrated below:

![](https://i.imgur.com/TSpPBIg.png)

The idea is to create an API that returns a smaller amount of data for all the stocks you are watching instead of fetching all the data for all the stocks in your watchlist. This is an example of aggregation, field transformation and payload reduction and will reduce bandwidth, save battery life (on your Smartphone) and provide a better user experience since you are retrieving much less data until it is needed.

The API is shown below:

`GET /watchlist?stocklist=aapl,txn,amzn`

The query parameter, *stocklist*, is a list of stock symbols separated by commas (CSV). In the example above, we are requesting Apple (aapl), Texas Instruments (txn) and Amazon (amzn) stock quotes.

The data we'd like returned looks like this:

```javascript
[
    {
        "symbol": "AAPL",
        "lastPrice": 159.835,
        "change": 0.24501038
    },
    {
        "symbol": "TXN",
        "lastPrice": 177.34,
        "change": 1.0099945
    },
    {
        "symbol": "AMZN",
        "lastPrice": 3137.69,
        "change": 75.60986
    }
]   
```
