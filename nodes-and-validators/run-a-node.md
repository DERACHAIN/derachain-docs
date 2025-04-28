---
description: Guideline to run a full node on DERA chain
---

# Run a Node

## Dependencies

* [Ubuntu 22.04](https://releases.ubuntu.com/jammy/)
* [GCC](https://phoenixnap.com/kb/install-gcc-ubuntu)
* [Go v1.23.6](https://go.dev/doc/install)
* A public static IP

## Build the Node binary

1. Clone the AvalancheGo repository

```
git clone https://github.com/ava-labs/avalanchego.git
```

2. Compile binary

```
cd avalanchego
./scripts/build.sh
```

3. Create AvalancheGo service directory

```
sudo mkdir /var/lib/avalanchego
```

4. Copy executable to binary directory

```
sudo cp avalanchego/build/avalanchego /usr/local/bin/
sudo chmod 755 /usr/local/bin/avalanchego
```

5. Create AvalancheGo working directory

```
sudo mkdir /root/.avalanchego
sudo mkdir -p /root/.avalanchego/plugins
```

6. Download the subnet EVM from [official repository](https://github.com/ava-labs/subnet-evm)

```
wget https://github.com/ava-labs/subnet-evm/releases/download/v0.7.3/subnet-evm_0.7.3_linux_amd64.tar.gz
tar -xzvf subnet-evm_0.7.3_linux_amd64.tar.gz
```

7. Copy subnet EVM to AvalancheGo working directory

```
sudo cp subnet-evm_0.7.3_linux_amd64/subnet-evm /root/.avalanchego/plugins/mDVK6hF1rcPB2e7ftmYbMQgnYMnQSnnk7cUfu8dENAYqH9XJA
```

`mDVK6hF1rcPB2e7ftmYbMQgnYMnQSnnk7cUfu8dENAYqH9XJA` is the VMID of DERA chain.

8. Create chainConfigs directory

```
sudo mkdir -p /root/.avalanchego/chainConfigs/2XCTEc8CfNK9MtQWYMfgNt32QjZsZqq92LH7eTV5xY8YjY44du
```

`2XCTEc8CfNK9MtQWYMfgNt32QjZsZqq92LH7eTV5xY8YjY44du` is blockchain ID of DERA chain.

9. Create chain `config.json`&#x20;

```
sudo touch /root/.avalanchego/chainConfigs/2XCTEc8CfNK9MtQWYMfgNt32QjZsZqq92LH7eTV5xY8YjY44du/config.json
```

with content.

```
{
  "database-type": "leveldb",
  "log-level": "debug",
  "warp-api-enabled": true,
  "eth-apis": [
    "eth",
    "eth-filter",
    "net",
    "admin",
    "web3",
    "internal-eth",
    "internal-blockchain",
    "internal-transaction",
    "internal-debug",
    "internal-account",
    "internal-personal"
  ]
}
```

10. Create `config.json` for AvalancheGo

```
sudo touch /root/.avalanchego/config.json
```

with content.

```
{
    "chain-config-dir": "/root/.avalanchego/chainConfigs",
    "http-allowed-hosts": "*",
    "http-host": "0.0.0.0",
    "network-allow-private-ips": "true",
    "public-ip": "YOUR_PUBLIC_IP",
    "track-subnets": "B7hA9WibSJu2fKdHT2XZs2RYg1rZTtxwg6cMYBKYjvcJjbqsp"
}
```

11. Create systemd startup scripts

```
sudo touch /etc/systemd/system/avalanchego.service
```

with content.

```
[Unit]
Description=AvalancheGo node
After=network.target

[Service]
User=root
ExecStart=/usr/local/bin/avalanchego --config-file /root/.avalanchego/config.json
WorkingDirectory=/var/lib/avalanchego
Restart=always
RestartSec=3
LimitNOFILE=65535
LimitNPROC=65535
LimitMEMLOCK=infinity

[Install]
WantedBy=multi-user.target
```

12. Load the systemd service

```
sudo systemctl daemon-reload
```

13. Start and enable the AvalancheGo service

```
sudo systemctl start avalanchego
sudo systemctl enable avalanchego
```

14. Tracking the bootstrap process, until the node is fully bootstrapped

```
sudo journalctl -u avalanchego
```

15. Verify node is fully bootstrapped

* DERA chain

```
curl -X POST --data '{
    "jsonrpc":"2.0",
    "id"     :1,
    "method" :"info.isBootstrapped",
    "params": {
        "chain":"2XCTEc8CfNK9MtQWYMfgNt32QjZsZqq92LH7eTV5xY8YjY44du"
    }
}' -H 'content-type:application/json;' 127.0.0.1:9650/ext/info
```

* P-chain

```
curl -X POST --data '{
    "jsonrpc":"2.0",
    "id"     :1,
    "method" :"info.isBootstrapped",
    "params": {
        "chain":"P"
    }
}' -H 'content-type:application/json;' 127.0.0.1:9650/ext/info
```

Ensure that both requests response are

```
{"jsonrpc":"2.0","result":{"isBootstrapped":true},"id":1}
```

Then your node is ready to work to secure DERA chain consensus.
