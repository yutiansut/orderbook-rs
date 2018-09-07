# orderbook-rs

I did this orderbook in addition to <https://github.com/inv2004/coinbase-pro-rs>

For performance I put it in flat array, that is why it uses memory actively.
For current coinbase BTC-USD pair it takes 188.1 Mb or RAM.

It has hardcoded limit for 20000(max price) * 100(cents) = 2*10^6 values it can store.
Call the OB with values which are outside these boundaries will return None,
but, I suppose, this return can be ignored in most cases.

It implements Display with the following output:
```
OB: volume of bids in 1-cent step | bid-price    ask-price | valume of asks in 1-cent step
OB: 0,0,0,0,0,0,0,0.001,0,0,0,0,0,0,0,0,0,0,0,5.5,26.047638720000013 | 6494.98   6494.99 | 5.006541749999999,10.0838,0,0,0,0,0,0,0.00130864,0.0052,0,0,0,0,0,0,0,0,0,0,0
```

## Examples
- Coinbase orderbook with reload if sequence is missed:

  <https://github.com/inv2004/orderbook-rs/blob/master/examples/coinbase.rs>
