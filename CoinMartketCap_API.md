# CoinMarketCap Crypto Data (ONLY FOR DAREC)

## This is a guidance help you access and retrieve data from CoinMarketCap

| API Endpoints |  Endpoints Details  |
| ------------- | ---------- |
| `CoinMarketCap ID map` | `/v1/cryptocurrency/map` |
| `Metadata` | `/v2/cryptocurrency/info` |
| `Latest listings` | `/v1/cryptocurrency/listings/latest` |
| `Historical listings` | `/v1/cryptocurrency/listings/historical` |
| `Latest quotes` | `/v2/cryptocurrency/quotes/latest` |
| `Historical quotes` | `/v2/cryptocurrency/quotes/historical` |
| `Latest market pairs` | `/v2/cryptocurrency/market-pairs/latest` |
| `Latest OHLCV` | `/v2/cryptocurrency/ohlcv/latest` |
| `Historical OHLCV` | `/v2/cryptocurrency/ohlcv/historical` |
| `Price performance Stats` | `/v2/cryptocurrency/price-performance-stats/latest` |
| `Categories` | `/v1/cryptocurrency/categories` |
| `Category` | `/v1/cryptocurrency/category` |
| `Airdrops` | `/v1/cryptocurrency/airdrops` |
| `Airdrop` | `/v1/cryptocurrency/airdrop` |
| `Trending Latest` | `/v1/cryptocurrency/trending/latest` |
| `Trending Most Visited` | `/v1/cryptocurrency/trending/most-visited` |
| `Trending Gainers & Losers` | `/v1/cryptocurrency/trending/gainers-losers` |


## Sample code for retrieving data from CoinMarketCap

Python file - Coin_Market_Data.py - will be used to do this work.

1. You shall go to the [CoinMarketAPI documents first](https://coinmarketcap.com/api/documentation/v1/#tag/cryptocurrency)
1. Then go through the endpoint you want to apply for 
1. Take a look at the `Parameters` 
1. Apply both endpoints url and parameters in code to get data you want

Example of OHLCV Historical v2 endpoint (`https://pro-api.coinmarketcap.com/v2/cryptocurrency/ohlcv/historical`) :

-  Look for parameters 
  ![Parameter_pic](sd)
  
-  Apply parameters 

```python
def get_crypto_data(endpoints : str) -> list:
	...
	# change parameters to apply endpoints functions
	parameters = {'id': '1', 'time_period':'hourly'}
	...
	
if __name__ == "__main__":
    # replace endpoints over here
    tmp_url = "/v2/cryptocurrency/ohlcv/historical"
    #tmp_url = ""
    tmp = get_crypto_data(tmp_url)
    print(tmp)
```

&nbsp; &nbsp; &nbsp; &nbsp; Results : 
```bash
{'status': {'timestamp': '2023-01-31T15:43:06.855Z', 'error_code': 0, 'error_message': None, 'elapsed': 31, 'credit_count': 1, 'notice': None}, 'data': {'id': 1, 'name': 'Bitcoin', 'symbol': 'BTC', 'quotes': [{'time_open': '2023-01-22T00:00:00.000Z', 'time_close': '2023-01-22T00:59:59.999Z', 'time_high': '2023-01-22T00:31:00.000Z', 'time_low': '2023-01-22T00:04:00.000Z', 'quote': {'USD': {'open': 22777.986661421615, 'high': 22924.725258810282, 'low': 22766.015550451917, 'close': 22880.744844720433, 'volume': 32632969494.79, 'market_cap': 440884496263.95, 'timestamp': '2023-01-22T00:59:59.999Z'}}}, {'time_open': '2023-01-23T00:00:00.000Z', 'time_close': '2023-01-23T00:59:59.999Z', 'time_high': '2023-01-23T00:40:00.000Z', 'time_low': '2023-01-23T00:19:00.000Z', 'quote': {'USD': {'open': 22721.088671950587, 'high': 22783.30898369253, 'low': 22681.005615044236, 'close': 22752.0464288741, 'volume': 24583793970.93, 'market_cap': 438426246672.8, 'timestamp': '2023-01-23T00:59:59.999Z'}}}, {'time_open': '2023-01-24T00:00:00.000Z', 'time_close': '2023-01-24T00:59:59.999Z', 'time_high': '2023-01-24T00:40:00.000Z', 'time_low': '2023-01-24T00:08:00.000Z', 'quote': {'USD': {'open': 22929.627735671096, 'high': 22998.174863006512, 'low': 22901.21255401255, 'close': 22980.99414544396, 'volume': 26427677869.25, 'market_cap': 442860694175.4, 'timestamp': '2023-01-24T00:59:59.999Z'}}}, {'time_open': '2023-01-25T00:00:00.000Z', 'time_close': '2023-01-25T00:59:59.999Z', 'time_high': '2023-01-25T00:49:00.000Z', 'time_low': '2023-01-25T00:28:00.000Z', 'quote': {'USD': {'open': 22639.26716752375, 'high': 22694.05085214261, 'low': 22542.67405416031, 'close': 22674.657406145838, 'volume': 26926708022.8, 'market_cap': 436975635212.81, 'timestamp': '2023-01-25T00:59:59.999Z'}}}, {'time_open': '2023-01-26T00:00:00.000Z', 'time_close': '2023-01-26T00:59:59.999Z', 'time_high': '2023-01-26T00:56:00.000Z', 'time_low': '2023-01-26T00:31:00.000Z', 'quote': {'USD': {'open': 23108.954486797436, 'high': 23225.158396047133, 'low': 23084.71778492542, 'close': 23218.235490506246, 'volume': 30738410938.59, 'market_cap': 447476624389.05, 'timestamp': '2023-01-26T00:59:59.999Z'}}}, {'time_open': '2023-01-27T00:00:00.000Z', 'time_close': '2023-01-27T00:59:59.999Z', 'time_high': '2023-01-27T00:13:00.000Z', 'time_low': '2023-01-27T00:59:00.000Z', 'quote': {'USD': {'open': 23030.717285647723, 'high': 23068.269038676288, 'low': 22935.586227386022, 'close': 22935.586227386022, 'volume': 25809870522.08, 'market_cap': 442051727552.7, 'timestamp': '2023-01-27T00:59:59.999Z'}}}, {'time_open': '2023-01-28T00:00:00.000Z', 'time_close': '2023-01-28T00:59:59.999Z', 'time_high': '2023-01-28T00:46:00.000Z', 'time_low': '2023-01-28T00:19:00.000Z', 'quote': {'USD': {'open': 23079.96433256669, 'high': 23165.895884287078, 'low': 23059.411053950033, 'close': 23155.41713637877, 'volume': 25199748476.31, 'market_cap': 446310824251.42, 'timestamp': '2023-01-28T00:59:59.999Z'}}}, {'time_open': '2023-01-29T00:00:00.000Z', 'time_close': '2023-01-29T00:59:59.999Z', 'time_high': '2023-01-29T00:55:00.000Z', 'time_low': '2023-01-29T00:20:00.000Z', 'quote': {'USD': {'open': 23031.4492355484, 'high': 23136.106332061998, 'low': 22985.0701306067, 'close': 23128.29144480638, 'volume': 14882566860.45, 'market_cap': 445812110882.76, 'timestamp': '2023-01-29T00:59:59.999Z'}}}, {'time_open': '2023-01-30T00:00:00.000Z', 'time_close': '2023-01-30T00:59:59.999Z', 'time_high': '2023-01-30T00:14:00.000Z', 'time_low': '2023-01-30T00:28:00.000Z', 'quote': {'USD': {'open': 23774.64896664247, 'high': 23789.347177699183, 'low': 23713.696022306456, 'close': 23772.692118385836, 'volume': 27524815093.63, 'market_cap': 458257271206.58, 'timestamp': '2023-01-30T00:59:59.999Z'}}}, {'time_open': '2023-01-31T00:00:00.000Z', 'time_close': '2023-01-31T00:59:59.999Z', 'time_high': '2023-01-31T00:53:00.000Z', 'time_low': '2023-01-31T00:39:00.000Z', 'quote': {'USD': {'open': 22840.796090600143, 'high': 22864.251766342062, 'low': 22765.56849944083, 'close': 22857.765464535485, 'volume': 27211970678.21, 'market_cap': 440640276591.64, 'timestamp': '2023-01-31T00:59:59.999Z'}}}]}}
```









