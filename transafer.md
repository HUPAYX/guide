# transter

#### using javascript
Refer to cosmosjs.md

```
const mnemonic = 'cccc';
const from_addr = 'aaaaa';
const to_addr = 'bbbb;
let tx = null;
const gas_fee: 400000; // uhpx
const gas: 50000; // hupx, gas_wanted in tx hash

try {
  let ecpairPriv = cosmos.getECPairPriv(mnemonic);
  let data = await cosmos.getAccounts(from_addr);
  let stdSignMsg = cosmos.NewStdMsg({
    type: 'cosmos-sdk/MsgSend',
    from_address: from_addr,
    to_address: to_addr,
    amountDenom: 'uhpx',
    amount: 500000, // uhpx
    feeDenom: 'uhpx',
    fee: gas_fee, // uhpx
    gas: gas, // uhpx
    memo: '',
    account_number: data.result.value.account_number,
    sequence: data.result.value.sequence
  });
  let signedTx = cosmos.sign(stdSignMsg, ecpairPriv, 'sync');

  tx = await cosmos.broadcast(signedTx);
  tx.txhash
} catch (err) {
  log(err);
  res.json(response(502));
  return;
}
```