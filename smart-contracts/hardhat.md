---
description: Guideline on Hardhat config and deployment.
---

# Hardhat

## Hardhat config

1. Add chain config in `networks` section in `hardhat.config.js` file:

```
// hardhat.config.js
networks: {
    derachain: {
      chainId: 20240801,
      url: "https://rpc-testnet.derachain.com/ext/bc/2LZp9ypK4SWm3a8MBYZbxTZgKbvB4aemUf83cBp1hSnvP7SFiw/rpc",
      accounts: [process.env.PRIVATE_KEY!],
    },
}
```

2. Add customChain config for contracts verification in `etherscan` section of `hardhat.config.js` file:

```
// hardhat.config.js
etherscan: {
    apiKey: {
      derachain: "empty",
    },
    customChains: [
      {
        network: "derachain",
        chainId: 20240801,
        urls: {
          apiURL: "https://trace.derachain.com/api",
          browserURL: "https://trace.derachain.com",
        },
      },
}
```

## Compile contracts

Compile smart contracts using hardhat commands as usual:

```
$ npx hardhat clean && npx hardhat compile
```

## Deploy contracts

Deploy compiled smart contracts using deployment scripts as usual:

```
$ npx hardhat run <deployment-script.js> --network derachain
```

## Verify contracts

Verify deployed smart contracts using`verify` command as usual:

```
$ npx hardhat verify <deployed-address> --network derachain
```

After verification, the verified contracts can be displayed and interacted with on [Explorer site](https://trace.derachain.com/).
