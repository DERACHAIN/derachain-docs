---
description: SubQuery is the native Indexer that provides on-chain data on DERA chain
---

# SubQuery Indexer

We utilize SubQuery to provide a native Indexer supports for all Protocol and Dapps working on DERA chain.

## TESTNET

* Endpoint [https://indexer.derachain.com/](https://indexer.derachain.com/)
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
