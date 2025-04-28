# VaultChain Node Configuration: Network and Services

This directory contains essential configuration files and data required to ensure the availability and proper functioning of the VaultChain Node. It is divided into two main subdirectories: **endpoints** and **ports**. These configurations are specifically tailored for the VaultChain Mainnet to provide network connectivity and services to the node.

## Directory Structure

```
network/
└── services/
    ├── endpoints/
    └── ports/
```

### Subdirectories:

#### 1. **endpoints/**

The **endpoints** directory contains configuration files for the different network endpoints that the VaultChain Node communicates with. These endpoints provide the necessary connections to the VaultChain Mainnet and facilitate data exchange between the node and the network. Ensure that the endpoint URIs listed in this directory are accurate and up-to-date to maintain proper functionality.

- Example file: `mainnet_endpoints.json`
- Content: Network URLs or IPs that the VaultChain Node will interact with.

#### 2. **ports/**

The **ports** directory contains configuration files related to the specific ports that the VaultChain Node listens on for network communications. These ports are essential for connecting to the VaultChain Mainnet and should be configured to match the network settings required for successful operation.

- Example file: `mainnet_ports.json`
- Content: Port numbers or ranges necessary for the VaultChain Node’s communication with the network.

## Usage

- **endpoints**: The endpoint configuration files should include the correct URLs for the VaultChain services you need the node to interact with, such as the VaultChain API and other essential services.
  
- **ports**: The port configuration files define the network ports that the VaultChain Node will use to send and receive data. Ensure that these ports are properly mapped and not blocked by firewalls or other network restrictions.

These configurations are vital to ensure that your VaultChain Node is properly connected to the network and can perform essential functions without disruptions.

## Additional Notes

- Always verify that the ports and endpoints are up-to-date, especially in case of network upgrades or changes in the VaultChain infrastructure.
- If any of the configurations are modified, restart the VaultChain Node for the changes to take effect.