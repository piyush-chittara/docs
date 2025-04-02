---
icon: code
---

# SDK



> * Main Net SDK: [https://www.npmjs.com/package/streamnft-evm](https://www.npmjs.com/package/streamnft-evm)
> * Test Net SDK: [https://www.npmjs.com/package/streamnft-evm-test](https://www.npmjs.com/package/streamnft-evm-test)

#### Import Statement

```jsx
import * as stream from "streamnft-evm";
```

Initialise SDK with API key

```jsx
stream.initializeSDK(API_KEY)
```

* Get all rented collection NFTs by user wallet

```javascript
let nfts= indexerCall(wallet.address) // indexer call to get nfts by wallet
nfts.push.apply(nfts, await stream.getNFTs(chainId,wallet.address));
```

* Get all rented NFTs by user wallet

```javascript
let nfts= indexerCall(wallet.address) // indexer call to get nfts by wallet
nfts.push.apply(nfts, await stream.getNFTs(chainId,wallet.address));
```
