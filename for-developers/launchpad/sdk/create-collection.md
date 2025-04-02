# Create Collection

### Create Collection

The `launchToken` function from the **Launchpad SDK** is used to create collection of various types of tokens (ERC-721, ERC-1155, SoulBound, Certificate) on the blockchain. It handles public and private minting conditions based on the token type.

***

#### 🔧 Function Signature

```jsx
async function launchToken(
  tokenType,
  _name,
  _symbol,
  _maxSupply,
  price,
  _tokenURI,
  chainId,
  signer,
  contractAddress,
  env
)

```

***

<details>

<summary>📄 Parameters</summary>

* **tokenType** (number): Specifies the type of token to deploy. Possible values:
  * `TokenType.SoulBoundPrivate` (0)
  * `TokenType.ERC1155Public` (1)
  * `TokenType.ERC1155Private` (2)
  * `TokenType.ERC721Public` (3)
  * `TokenType.ERC721Private` (4)
  * `TokenType.Certificate` (5)

- **\_name** (string): The name of the token/collection.

* **\_symbol** (string): The symbol of the token (e.g., `ETH`, `MATIC`).

- **\_maxSupply** (number | ethers.MaxUint256): Maximum token supply. Not needed for ERC 1155 as it will be set later for each NFTs.

* **price** (number): Minting price for ERC 721 public tokens. Set to `0` for private tokens,ERC 1155(later will set for each NFTs) and certificates.

- **\_tokenURI** (string): URI for metadata, required only for **Certificate** tokens. Use an empty string for other types.

* **chainId** (number): The chain ID of the network where the token is deployed.

- **signer** (ethers.Signer): Ethers.js signer object for transaction signing.

* **contractAddress** (string): The address of the deployed contract.

- **env** (string): The environment to use (`testnet` or `mainnet`).

</details>

<details>

<summary>✅ Example Usage</summary>

#### 1. SoulBound Private Token:

```jsx
await launchToken(
  TokenType.SoulBoundPrivate,
  'MySoulBoundToken',
  'SBT',
  5000,
  0,
  '',
  1,  // Ethereum Mainnet
  signer,
  '0xContractAddress',
  undefined
);

```

#### 2. ERC-1155 Public Token:

```jsx
await launchToken(
  TokenType.ERC1155Public,
  'GameAssets',
  'GMA',
  0,
  0,
  '',
  137,  // Polygon Mainnet
  signer,
  '0xContractAddress',
  undefined
);

```

#### 3. ERC-1155 Private Token:

```jsx
await launchToken(
  TokenType.ERC1155Private,
  'PrivateAssets',
  'PVA',
  0,
  0,
  '',
  137,  // Polygon Mainnet
  signer,
  '0xContractAddress',
  undefined
);

```

#### 4. ERC-721 Public Token:

```jsx
await launchToken(
  TokenType.ERC721Public,
  'ArtGallery',
  'ART',
  1000, 
  ethers.utils.parseEther('0.1'), //in smallest unit of that currency
  '',
  1,  // Ethereum Mainnet
  signer,
  '0xContractAddress',
  undefined
);

```

#### 5. ERC-721 Private Token:

```jsx
await launchToken(
  TokenType.ERC721Private,
  'VIPArt',
  'VIP',
  200,
  0,
  '',
  1,  // Ethereum Mainnet
  signer,
  '0xContractAddress',
undefined
);

```

#### 6. Certificate Token:

</details>

####
