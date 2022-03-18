# cosmos library

#### Pakage Download
npm install @cosmostation/cosmosjs@0.4.1

#### Using Library
- cosmosjs
```
const cosmosjs = require("@cosmostation/cosmosjs");

const lcdUrl  = "lcd.hupay.io"
const chainId = "hupayx-hub";
const cosmos = cosmosjs.network(lcdUrl, chainId);
module.exports = cosmos;
```
