# NFTs (Rented)

## **Using External Indexer**

_Query Parameters specific for rentals_**:**

* `collection`: Filter for token address of the NFT collection
* `rentee`: Filter for assets rented by a wallet
* `state`: Filter for all assets on Marketplace (STALE) or rented out (RENT)
* `onlyRentData` : Output only rental data (NFT rentee, NFT owner, rental expiry, state)

{% openapi src="../../../.gitbook/assets/openapi (2).yml" path="/assetManager/{chainId}" method="get" %}
[openapi (2).yml](<../../../.gitbook/assets/openapi (2).yml>)
{% endopenapi %}

**Response:**

* Successful responses return an array of asset managers for provided token address with detailed information, such as the current rentee and the state of each asset.

### Example: How to Integrate with exiting **external NFT indexer**

* Get all rented collection NFTs by user wallet

```javascript
let nfts= indexerCall(wallet.address) // indexer call to get nfts by wallet
nfts.push.apply(nfts, await getNFTs(chainId,wallet.address,tokenAddress));

async function getNFTs(chainId, address,tokenAddress){
    const nfts = await fetch(`https://api.danlabs.xyz/assetManager/${chainId}?user=${walletAddress}&collection=${collectionAddress}`)
    .then(response => {
        if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
        }
        return response.json();
    })
    .catch(error => {
        // Handle network errors or API response errors here
        console.error('Error:', error.message);
    });
    return nfts;
}
```

* Get all rented NFTs by user wallet

```javascript
let nfts= indexerCall(wallet.address) // indexer call to get nfts by wallet
nfts.push.apply(nfts, await getNFTs(chainId,wallet.address));

async function getNFTs(chainId, address){
    const nfts = await fetch(`https://api.danlabs.xyz/assetManager/${chainId}?user=${walletAddress}`)
    .then(response => {
        if (!response.ok) {
        throw new Error(`HTTP error! Status: ${response.status}`);
        }
        return response.json();
    })
    .catch(error => {
        // Handle network errors or API response errors here
        console.error('Error:', error.message);
    });
    return nfts;

```
