---
description: Smart contracts development using Foundry
---

# Foundry

## Compile

The smart contracts should be compiled as usual.

```
$ forge build
```

## Deploy

```
$ forge create \
--rpc-url <derachain-rpc-url> \
[--constructor-args <arg1> <arg2> ...] \
--private-key <deployer-private-key> \
path/to/Contract.sol:ContractName
```

## Verify

```
$ forge verify-contract \
--rpc-url <derachain-rpc-url> \
[--constructor-args $(cast abi-encode "constructor(type1,type2,...)" arg1 arg2 ...)] \
--verifier blockscout \
--verifier-url 'https://trace.derachain.com/api/' \
<deployed-address> \
path/to/Contract.sol:ContractName
```
