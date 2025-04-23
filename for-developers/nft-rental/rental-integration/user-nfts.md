# NFTs (Owned and Rented)

## **Use StreamNFT Indexer (1 API Call to get all User NFTs)**

{% openapi src="../../../.gitbook/assets/openapi3.yml" path="/getNFTs/{chainId}/{wallet}" method="get" %}
[openapi3.yml](../../../.gitbook/assets/openapi3.yml)
{% endopenapi %}

**Response:**

* Successful responses return an array of NFT data for provided token address with detailed information, such as the current rentee and the state of each asset.
