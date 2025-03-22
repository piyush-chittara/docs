# NFTs (Owned and Rented)

## **Use StreamNFT Indexer (1 API Call to get all User NFTs)**

{% openapi src="../../../.gitbook/assets/openapi3.yml" path="/getNFTs/{chainId}/{wallet}" method="get" %}
[openapi3.yml](../../../.gitbook/assets/openapi3.yml)
{% endopenapi %}

## **2. Use External Indexer (2 API Call to get all User NFTs)**

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
