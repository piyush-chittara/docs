---
description: Purchase an NFT from the marketplace
---

# Buy Listed NFT

#### Parameters

| Parameter         | Type                | Description                               |
| ----------------- | ------------------- | ----------------------------------------- |
| `tokenAddress`    | `string`            | NFT contract address                      |
| `tokenId`         | `number`            | Token ID of the NFT                       |
| `chainId`         | `number`            | Blockchain chain ID                       |
| `fungibleIndex`   | `number`            | Index for fungible tokens (0 for ERC-721) |
| `count`           | `number`            | Quantity to buy                           |
| `signer`          | `object`            | Wallet signer                             |
| `contractAddress` | `string` (optional) | Marketplace contract address              |

#### Example Usage

```jsx
import { buyListedNFT } from "streamnft-evm";

const response = await buyListedNFT(
  "0x1234...abcd", // tokenAddress
  1,               // tokenId
  656476,          // Chain ID
  0,               // fungibleIndex (0 for ERC-721)
  1,               // count
  signer           // Ethers signer
);
```

Optional: How to get singer using `streamnft-evm` SDK

```javascript
import { getSigner, getWalletSigner } from "streamnft-evm";

const signer = await getSigner(
chainId, 
privateKey, 
rpcUrl // optional for private rpc
);

const signer = await getWalletSigner(); // for wallet pop-up
```
