---
description: List an NFT for sale on the marketplace
---

# Create Listing

#### Parameters

| Parameter         | Type                | Description                  |
| ----------------- | ------------------- | ---------------------------- |
| `tokenAddress`    | `string`            | NFT contract address         |
| `tokenId`         | `number`            | Token ID of the NFT          |
| `salePrice`       | `string`            | Price of the NFT in Wei      |
| `count`           | `number`            | Quantity (for ERC-1155)      |
| `chainId`         | `number`            | Blockchain chain ID          |
| `signer`          | `object`            | Wallet signer                |
| `contractAddress` | `string` (optional) | Marketplace contract address |

#### Example Usage

```jsx
import { createListing } from "streamnft-evm";

const response = await createListing(
  "0x1234...abcd",  // tokenAddress
  1,                // tokenId
  "1000000000000000000", // 1 EDU (give in atomic unit of the currency)
  1,                // count (1 for ERC-721)
  656476,           // Opencampus chain ID
  signer            // Ethers signer
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
