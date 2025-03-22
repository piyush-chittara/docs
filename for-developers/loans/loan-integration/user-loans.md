# User Loans

**Parameters:**

* `chainId`: The ID of the blockchain chain where the asset managers are deployed.

**Query Parameters specific for rentals:**

* `collection`: Filter for token address of the NFT collection
* `rentee`: Filter for assets rented by a wallet
* `state`: Filter for all assets on loan (LOAN)



{% openapi src="../../../.gitbook/assets/openapi (2).yml" path="/assetManager/{chainId}" method="get" %}
[openapi (2).yml](<../../../.gitbook/assets/openapi (2).yml>)
{% endopenapi %}

**Response:**

* Successful responses return an array of asset managers for provided token address with detailed information, such as the current rentee and the state of each asset.
