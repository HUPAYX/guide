# Transactions

#### Get Transaction Details
- URL
```
const path = "/txs/{hash}

url: /txs/{hash}
method: GET
query
  hash: tx hash(string)

Request URL
http://lcd.hupay.io/txs/${hash}
```
- Curl
```
curl -X GET "http://lcd.hupay.io/txs/{hash}" -H "accept: application/json"
```
- cosmosjs
```
Refer to cosmosjs.md

cosmos.checkTxs(tx_id);
```

#### Get Send Transaction list
```
url: /txs
method: GET
query
  message.action: send(string)
  message.sender: address(string)
  page: 1(number)
  limit: 1(number)


Maximum limit: 100

Request URL
http://lcd.hupay.io/txs?message.action=send&message.sender={address}=1&limit=100

Curl
curl -X GET "http://lcd.hupay.io/txs?message.action=send&message.sender={address}&page=1&limit=100" -H "accept: application/json"
```

#### Get Recipient Transaction list
- URL
```
url: /txs
method: GET
query
  message.action: send(string)
  transfer.recipient: address(string)
  page: 1(number)
  limit: 1(number)


Maximum limit: 100

Request URL
http://lcd.hupay.io/txs?message.action=send&transfer.recipient={address}&page={page}&limit={limit}
```
- Curl
```
curl -X GET "http://lcd.hupay.io/txs?message.action=send&transfer.recipient={address}&page={page}&limit={limit}" -H "accept: application/json"
```
- cosmosjs
```
Refer to cosmosjs.md

cosmos.searchTxs(page, limit, address);
```