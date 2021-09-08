# Flitpay 

# Flitpay Public Rest API
Here is our APIs that you can use to develop Ticker, price comparison apps, or anything that help your audience willing to be in frequent touch with crypto price updates.


## General Information
1. Base API Endpoint: https://api.flitpay.com/
1. All public api will return either JSON or Array object.

### Public API Endpoints

1. #### Market Status
   GET `/api/v2/market-status`  [Live link](https://api.flitpay.com/api/v1/market-status/)

    > Adding &quot;Market Status&quot; will give you the information of markets and assets. It is beneficial when you want to track the configuration of our market, track fees or status of withdrawal deposit, market configuration and more. It does not give you the freedom to access price polling, as, under uncertainties, there may occur a delay. If you are looking for price polling, you can use our price ticker API.
    
    The response object will have two keys:
      1. Market: All market-related configs will be in this key
      2. Asset: All assets-related configs will be here 
    ### Response:
    ```
    {
    "markets": [
        {
            "baseMarket": "INR",
            "tradeMarket": "XRP",
            "minBuyAmount": 1.0,
            "minSellAmount": 1.0,
            "fee": {
                "bid": {
                    "maker": 0.2,
                    "taker": 0.2
                },
                "ask": {
                    "maker": 0.2,
                    "taker": 0.2
                }
            },
            "basePrecision": 4,
            "tradePrecision": 2,
            "low": "80.37790000",
            "high": "101.18390000",
            "last": "5091507.00000000",
            "open": 101.1839,
            "volume": "1394827.98746617",
            "sell": "154.20910000",
            "buy": "30.53300000",
            "type": "SPOT",
            "status": "active"
        },
        {
            "baseMarket": "INR",
            "tradeMarket": "BTC",
            "minBuyAmount": 0.0001,
            "minSellAmount": 0.0001,
            "fee": {
                "bid": {
                    "maker": 0.2,
                    "taker": 0.2
                },
                "ask": {
                    "maker": 0.2,
                    "taker": 0.2
                }
            },
            "basePrecision": 0,
            "tradePrecision": 6,
            "low": "3379182.00000000",
            "high": "3970054.00000000",
            "last": "5091507.00000000",
            "open": 3964691.0,
            "volume": "274.33563300",
            "sell": "4071067.00000000",
            "buy": "100.00000000",
            "type": "SPOT",
            "status": "active"
        },
    ],
    "assets": [
        {
            "type": "FLT",
            "name": "Flitpay Token",
            "withdrawFee": 100.0,
            "minWithdrawAmount": 0.0,
            "maxWithdrawAmount": 0.0,
            "minDepositAmount": 0.0,
            "maxDepositAmount": 0.0,
            "confirmation": 25,
            "deposit": "False",
            "withdrawal": "False"
        },
        {
            "type": "DOGE",
            "name": "DOGECOIN",
            "withdrawFee": 4.0,
            "minWithdrawAmount": 5.0,
            "maxWithdrawAmount": 100000.0,
            "minDepositAmount": 0.0,
            "maxDepositAmount": 100000.0,
            "confirmation": 0,
            "deposit": "False",
            "withdrawal": "False"
        },
    ]
}
    ```
    
    
    1. **`Markets Key` It has multiple market-related configurations, and the description of every field in the market is as below:**
    
        1. `baseMarket`: ticker code of base asset
        1. `tradeMarket`: ticker code of Trade asset
        1. `minBuyAmount`: Minimum buy amount of base asset
        1. `minSellAmount`: Minimum sell amount of base asset
        1. `fee`: JSON Object consists of `bid` and `ask` order's maker-taker fee percentage
        1. `basePrecision`: Maximum precision of base asset, this the decimal point. 
        1. `tradePrecision`: Maximum  precision of Trade asset
        1. `low`: 24 hrs lowest price of base asset
        1. `high`: 24 hrs highest price of base asset
        1. `last`: Last traded price in current market
        1. `open`: Market Open price 24hrs ago
        1. `volume`: Last 24hrs traded volume
        1. `sell`: Top ask order price
        1. `buy`: Top bid order price
        1. `type`: This defines the type of market, currently we have `SPOT` and `P2P`
        1. `status`: This defines the current state of the market. This can be `active` or `suspended`
    1. **`assets` key have multiple asset related configuration as described below:**
    
        1. `type`: asset code
        1. `name`: Display name of asset
        1. `withdrawFee`: Withdrawal fee of asset
        1. `minWithdrawAmount`: Minimum withdrawal amount in a single transaction
        1. `maxWithdrawAmount`: Maximum withdrawal amount in a single transaction
        1. `minDepositAmount`: This is the min Deposit amount that will be accepted as deposit
        1. `maxDepositAmount1: This is the max Deposit amount that will be accepted as deposit
        1. `confirmations`: Is the min number of block height needed to confirm a block chain deposit transaction.
        1. `deposit`: Denotes whether deposit is enabled or disabled
        1. `withdrawal`: Denotes whether withdrawal is enabled or disabled
        
