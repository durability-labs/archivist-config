# Archivist configuration

 Repository contains configuration files for Archivist and internal service.


 All files can be accessed via https://config.archivist.storage endpoint.


## Configuration files

 - `testnet.json` - Testnet services configuration file.

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

### [DiscordBot](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/BiblioTech)
Uses "team"/"nodes" to automatically replace the known nodes Eth address with user-friendly names in discord messages.
Uses "rpcs" to connect to RPC provider.
Uses "marketplace" to access contract address and ABI to power its mint/balance features.

### [TraceContract](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/TraceContract)
Uses "team"/"nodes" to automatically replace the known nodes Eth address with user-friendly names in output.
Uses "rpcs" to connect to RPC provider.
Uses "marketplace" to access contract address and ABI to read event logs and decode block transactions.
Uses "team"/"nodes" to find all host nodes and their podName values.
Uses "team"/"utils" elastic search endpoint to retrieve node logs.

### [TestnetRewarder](https://github.com/durability-labs/cs-archivist-dist-tests/tree/main/Tools/TestNetRewarder)
Uses "rpcs" to connect to RPC provider.
Uses "marketplace" to access contract address and ABI to read event logs and decode block transactions.

