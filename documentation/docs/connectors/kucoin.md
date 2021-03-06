# KuCoin Connector

!!! Note "As of 01/22/2020"
    This connector is currently available in development version only and will be in the upcoming 0.23.0 release.


## About KuCoin

KuCoin is a centralized exchange based in Hong Kong that opened for cryptocurrency trading in September 2017. Nicknamed the "People's Exchange"​, Kucoin is easy to use for novice investors and in-depth enough for crypto enthusiasts. 

It has one of the world’s most impressive trading pair selections, a wide range of alt coins with more than 300 trading pairs and are adding new ones regularly. The exchange has its own cryptocurrency, KuCoin Shares (KCS).


## Using the Connector

Because [KuCoin](https://www.kucoin.com/) is a centralized exchange, you will need to generate and provide your API keys in order to trade using Hummingbot.

```
Enter your KuCoin API key >>>
Enter your KuCoin secret key >>>
Enter your KuCoin passphrase >>>
```

Private keys and API keys are stored locally for the operation of the Hummingbot client only. At no point will private or API keys be shared to CoinAlpha or be used in any way other than to authorize transactions required for the operation of Hummingbot.

!!! tip "Copying and pasting into Hummingbot"
    See [this page](https://docs.hummingbot.io/support/how-to/#paste-items-from-clipboard-in-putty) for more instructions in our Get Help section.


### Creating KuCoin API keys

This FAQ article below in their documentation shows step-by-step instructions on how to create API keys in KuCoin exchange.

* [How to create an API](https://kucoin.zendesk.com/hc/en-us/articles/360015102174-How-to-Create-an-API)

!!! warning "API key permissions"
    We recommend using only **"trade"** enabled API keys; enabling **"withdraw", "transfer", or the equivalent** is unnecessary for current Hummingbot strategies.


## Miscellaneous Info

### Minimum Order Sizes

Minimum order size varies per market. All minimum trade quantities can be found in the following public API:

```
https://api.kucoin.com/api/v1/symbols
```

The size must be greater than the `baseMinSize` for the symbol and no larger than the `baseMaxSize`. For example, trading pair ETH-USDT minimum order size is 0.0001 ETH.

```
"symbol": "ETH-USDT",
"quoteMaxSize": "999999999",
"enableTrading": true,
"priceIncrement": "0.01",
"feeCurrency": "USDT",
"baseMaxSize": "10000000000",
"baseCurrency": "ETH",
"quoteCurrency": "USDT",
"market": "USDS",
"quoteIncrement": "0.000001",
"baseMinSize": "0.0001",
"quoteMinSize": "0.01",
"name": "ETH-USDT",
"baseIncrement": "0.0000001",
"isMarginEnabled": true
```

!!! tip
    See troubleshooting section on how to [Get REST API data using Postman](/support/how-to/#get-rest-api-data-using-postman).


### Transaction Fees

Generally, KuCoin charges 0.10% on both maker and taker while a user can get 20% discount on trading fees if paid in KCS. However, users who trade high volumes and own substantial amounts of KuCoin Shares can receive more discounts.

Read through their articles below related to trading fees, and rebates.

* [VIP Level](https://www.kucoin.com/vip/level)
* [Pay Fees via KCS & Enjoy 20% Off](https://kucoin.zendesk.com/hc/en-us/articles/360037007974-Pay-Fees-via-KCS-Enjoy-20-Off)