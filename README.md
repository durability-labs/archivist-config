# Archivist configuration

 Repository contains configuration files for Archivist and internal service.

 All files can be accessed via https://config.archivist.storage endpoint.

## Configuration files
 - `testnet.json` - Testnet services configuration file.
 - `devnet.json` - Devnet services configuration file.

## Text endpoints
We are generating text endpoints to simplify usage and do not use JSON parsing tools
```shell
# Testnet
curl -s https://config.archivist.storage/devnet/spr
curl -s https://config.archivist.storage/testnet/marketplace

# Devnet
curl -s https://config.archivist.storage/devnet/spr
curl -s https://config.archivist.storage/devnet/marketplace
```

## Usage
Applications listed below will use the config.archivist.storage endpoint, and will respond to the following environment-variables:
| Variable | Description |
|----------|-------------|
| ARCHIVIST_NETWORK | Archivist network to be used. Optional. Default: "testnet" |
| ARCHIVIST_VERSION | Archivist version to be used. Optional. Default: "latest" |
| ARCHIVIST_CONFIG_URL | Optional override. If set, use this URL to fetch config JSON. |
| ARCHIVIST_CONFIG_FILE | Optional override. If set, use this filepath to read config JSON. |

## Applications
These applications use the config.archivist.endpoint in the following ways.

### [Crawler](https://github.com/durability-labs/archivist-network-crawler)
- Uses "team"/"utils" to connect to the crawler RPC endpoint.
- Uses "marketplace" to access contract address.
- Uses "sprs" to set up a DHT node.

### [DiscordBot](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/BiblioTech)
- Uses "team"/"nodes" to automatically replace the known nodes Eth address with user-friendly names in discord messages.
- Uses "team"/"utils" to connect to the bot RPC endpoint.
- Uses "marketplace" to access contract address and ABI to power its mint/balance features.

### [TraceContract](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/TraceContract)
- Uses "marketplace" to access contract address and ABI to read event logs and decode block transactions.
- Uses "team"/"nodes" to automatically replace the known nodes Eth address with user-friendly names in output.
- Uses "team"/"nodes" to find all host nodes and their podName values.
- Uses "team"/"utils" to connect to the bot RPC endpoint.
- Uses "team"/"utils" elastic search endpoint to retrieve node logs.

### [TestnetRewarder](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/TestNetRewarder)
- Uses "team"/"utils" to connect to the bot RPC endpoint.
- Uses "marketplace" to access contract address and ABI to read event logs and decode block transactions.
