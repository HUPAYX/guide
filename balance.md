# Get account balances

#### Unit Converter
1 hpx = 100000 uhpx
base: hpx


#### Using Get Balance
- url
```
url: /bank/balances/{address}
method: GET
query
  address: address in bech32 format
```
- cosmosjs
```
Refer to cosmosjs.md

cosmos.getBalance(address);
```

You can sometimes find 'uhx' but not used.