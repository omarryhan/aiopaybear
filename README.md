<p align="center">
  <img src="https://avatars0.githubusercontent.com/u/47103595?s=460&v=4" alt="Logo" width="200" height="200"/>
  <p align="center">
    <a href="https://github.com/omarryhan/aiopaybear"><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href="https://pepy.tech/badge/aiopaybear"><img alt="Downloads" src="https://pepy.tech/badge/aiopaybear"></a>
    <a href="https://pepy.tech/badge/aiopaybear/month"><img alt="Monthly Downloads" src="https://pepy.tech/badge/aiopaybear/month"></a>
  </p>
</p>

# Aiopaybear

Async client for savvy.io (FKA paybear.io)

## Setup

    $ pip install aiopaybear

## Dependencies

- aiohttp

## Usage

**Init**:

    from aiopaybear impory Aiopaybear

    aiopaybear = Aiopaybear(
        token='your_savvyio_token',
        public_key='your_savvyio_public_key',
        callback_url='https://yourwebsite/savvy/callback'
    )

**Get list of enabled currencies**:

    >>> await aiopaybear.get_currencies()

**Create new payment**:

    >>> await aiopaybear.create_payment('btc')

    {
        "success": true,
        "data": {
            "invoice": "d1ddf6e3767030b08032cf2eae403600",
            "address": "0x2073eb3be1a41908e0353427da7f16412a01ae71"
        }
    }

**Get exchange rates of all supported currencies for a specific fiat currency**:

    >>> await aiopaybear.xrate_all('usd')

    {
        "success": true,
        "data": {
            "ltc": {
                "poloniex": 340.986909455,
                "hitbtc": 340.568,
                "bittrex": 340.25,
                "bitfinex": 341.295,
                "mid": 340.77497736375
            },
            "eth": {
                "poloniex": 804.580989955,
                "hitbtc": 805.88,
                "bittrex": 803.47641155,
                "bitfinex": 805.125,
                "mid": 804.76560037625
            },
            ...
        }
    }

**Get exchange rate of a single crypto currency**:

    >>> await aiopaybear.xrate('usd', 'btc')

    {
        "success": true,
        "data": {
            "poloniex": 301.71905,
            "bittrex": 302.05,
            "bitfinex": 301.53499,
            "mid": 301.76807
        }
    }

## Contact 📧

Like my work? Have an exciting product and think we can work together?

Let's talk. Send me an email @ omarryhan@gmail.com

## Buy me a coffee ☕

**Bitcoin:** 3NmywNKr1Lzo8gyNXFUnzvboziACpEa31z

**Ethereum:** 0x1E1400C31Cd813685FE0f6D29E0F91c1Da4675aE

**Bitcoin Cash:** qqzn7rsav6hr3zqcp4829s48hvsvjat4zq7j42wkxd

**Litecoin:** MB5M3cE3jE4E8NwGCWoFjLvGqjDqPyyEJp

**Paypal:** https://paypal.me/omarryhan
