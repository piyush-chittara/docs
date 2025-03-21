---
description: Remove an NFT from the marketplace
---

# Cancel Listing

#### Parameters

| Parameter         | Type                | Description                               |
| ----------------- | ------------------- | ----------------------------------------- |
| `tokenAddress`    | `string`            | NFT contract address                      |
| `tokenId`         | `number`            | Token ID of the NFT                       |
| `fungibleIndex`   | `number`            | Index for fungible tokens (0 for ERC-721) |
| `count`           | `number`            | Quantity to cancel                        |
| `chainId`         | `number`            | Blockchain chain ID                       |
| `signer`          | `object`            | Wallet signer                             |
| `contractAddress` | `string` (optional) | Marketplace contract address              |

#### Example Usage

<pre class="language-jsx"><code class="lang-jsx">import { cancelListing} from "streamnft-evm";
<strong>
</strong><strong>const response = await cancelListing(
</strong>  "0x1234...abcd", // tokenAddress
  1,               // tokenId
  0,               // fungibleIndex ( 0 for ERC721 )
  1,               // count
  656476,          // Chain ID
  signer           // Ethers signer
);
</code></pre>

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
