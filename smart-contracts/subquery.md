---
description: SubQuery is the native Indexer that provides data on DERA chain
---

# SubQuery

We utilize SubQuery to provide a native Indexer supports for all Protocol and Dapps working on DERA chain.

## TESTNET

* Endpoint [https://subquery.derachain.com](https://subquery.derachain.com/)
* Example query:

```graphql
# Write your query or mutation here
{
  collections(
    first: 5
    orderBy: [BLOCK_HEIGHT_DESC]
    filter: { chainId: { equalTo: 20240801 } }
  ) {
    nodes {
      chainId
      id
      blockHeight
      address
    }
  }

  nFTs(
    first: 5
    orderBy: [BLOCK_HEIGHT_DESC]
    filter: { chainId: { equalTo: 20240801 } }
  ) {
    nodes {
      chainId
      id
      blockHeight
      collection
      tokenId
      owner
    }
  }

  dataRegistries(
    first: 5
    orderBy: [BLOCK_HEIGHT_DESC]
    filter: { chainId: { equalTo: 20240801 } }
  ) {
    nodes {
      chainId
      id
    }
  }

  _metadata {
    dynamicDatasources
  }
}
```

## MAINNET

* TBA
