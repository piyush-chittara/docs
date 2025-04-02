# Mint NFT

### Mint Single NFT

The `mintNFT` function, imported from **streamnft-evm**, facilitates minting various types of tokens (ERC721, ERC1155, Certificate) on the Ethereum Virtual Machine (EVM). It supports both public and private minting methods for different token standards.

***

#### 🔧 Function Signature

```jsx
await mintNFT(
  tokenType,
  price,  // Price in Wei
  amount,  // Amount (irrelevant for ERC721)
  signature,  // Signature
  tokenUri,  // Token URI
  tokenId,  // Token ID
  chainId,  // Chain ID
  signer,
  contractAddress
);
```

***

<details>

<summary>📄 Parameters</summary>

* `tokenType` _(number, required)_: The type of token to be minted, specified in the `TokenType` enumeration.
* `price` _(BigInt | number, optional)_: The price per token in Wei for public minting. For private tokens, this is not required.
* `amount` _(number, optional)_: The quantity of tokens to mint (mainly for ERC1155).
* `signature` _(string, optional)_: A pre-approved signature required for ERC721Public minting.
* `tokenUri` _(string, optional)_: The metadata URI for the NFT.
* `tokenId` _(number, optional)_: The ID of the token to mint.
* `chainId` _(number, required)_: The chain ID where the contract is deployed.
* `signer` _(Signer, required)_: The wallet or account object initiating the transaction.
* `contractAddress` _(string, required)_: The address of the deployed NFT contract.

</details>

***

<details>

<summary>✅ Example Usage</summary>



**1. ERC721Public (Public Minting)**

* Required: `price`, `signature`, `tokenUri`, `tokenId`
* Example:

<pre class="language-jsx"><code class="lang-jsx">
<strong>await mintNFT(
</strong>  TokenType.ERC721Public,
  ethers.utils.parseEther("0.05"),  // Price in Wei
  1,  // Amount (irrelevant for ERC721)
  "0xValidSignature",  // Signature
  "&#x3C;https://example.com/metadata/1>",  // Token URI
  1,  // Token ID
  80001,  // Chain ID (Polygon Mumbai Testnet)
  signer,
  "0xContractAddress"
);

</code></pre>

**2. ERC721Private (Private Minting)**

* Required: `tokenUri`
* Example:

```jsx
await mintNFT(
  TokenType.ERC721Private,
  0,  // Price not required
  1,
  "",
  "<https://example.com/metadata/2>",
  2,
  80001,
  signer,
  "0xContractAddress"
);

```

**3. ERC1155Public (Public Minting)**

* Required: `price`, `amount`, `tokenId`
* Example:

```jsx

await mintNFT(
  TokenType.ERC1155Public,
  ethers.utils.parseEther("0.02"),
  10,  // Amount to mint
  "",
  "<https://example.com/metadata/3>",
  3,  // Token ID
  80001,
  signer,
  "0xContractAddress"
);

```

**4. ERC1155Private (Private Minting)**

* Required: `amount`, `tokenId`
* Example:

```jsx
await mintNFT(
  TokenType.ERC1155Private,
  0,
  5,  // Amount to mint
  "",
  "<https://example.com/metadata/4>",
  4,
  80001,
  signer,
  "0xContractAddress"
);

```

**5. Certificate (Owner-Only Minting)**

* No `price`, `amount`, or `tokenUri` required.
* Example:

```jsx
await mintNFT(
  TokenType.Certificate,
  0,
  1,
  "",
  "",
  0,
  80001,
  signer,
  "0xContractAddress"
);

```

</details>

***

#### Return Value

An object containing:

* `success` _(boolean)_: Indicates if minting was successful.
* `tokenType` _(number)_: The type of token minted.
* `transactionHash` _(string)_: The hash of the transaction.
* `error` _(string)_: Error message, if applicable.

***

#### Error Handling

* Throws **Invalid token type** if `tokenType` does not match a supported type.
* Throws **Unsupported token type** for SoulBound and ERC7066 tokens (not yet implemented).
* Catches and logs errors if the transaction fails.
