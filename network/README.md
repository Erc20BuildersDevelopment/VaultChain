# VaultChain Network Essentials

## Overview

The **VaultChain Network** is a decentralized blockchain network that ensures the stability, security, and scalability of the VaultChain ecosystem. The core components of the network include **Validator Nodes**, **Mainnet connections**, and various logs to monitor and maintain its health. This README outlines the key elements essential for ensuring the proper functioning of the VaultChain Mainnet, such as validator logs, connection logs, and other vital resources.

---

## Key Logs and Files

### 1. **Validator Logs (`validator_logs/`)**

Validator node logs are crucial for tracking the status and performance of nodes that participate in validating blocks and maintaining the integrity of the VaultChain Mainnet. The **validator logs** are saved in **JSON format** for easy analysis and troubleshooting.

- **`validator_log.json`**: This file records the actions and status of the validator node. It includes:
    - Validator node connection status (`Connected`, `Syncing`, `Failed`).
    - Block validation outcomes (success or failure).
    - VaultChain rewards earned by the validator node.
    - Errors and warnings related to the node's operation.

#### Example of `validator_log.json`:
```json
{
    "total_rewards": 2.57,
    "logs": [
        "[INFO] Node status: Connected",
        "[VALIDATED] Block validated successfully. Reward: 0.35 VaultChain Tokens",
        "[INFO] Node status: Syncing",
        "[ERROR] Block validation failed. Try again.",
        "[INFO] Validator Node stopped.",
        "[INFO] Logs saved to validator_log.json."
    ]
}
```

These logs are essential for maintaining a history of validator node performance, and they help administrators to review and assess node behavior. When the validator node is stopped, the logs and rewards are saved into this file to allow further inspection and report generation.

### 2. **Connection Logs (`connection_logs/`)**

Connection logs track the interactions of nodes within the VaultChain network. They monitor the connection state of various network components, including **RPC connections**, **Peer connections**, **Mainnet connections**, and **Beacon Chain connections**.

- **`connection_history.json`**: This file logs the following:
    - Connection attempts to different network components (e.g., peers, RPC servers).
    - The success or failure of each connection attempt.
    - Timestamps of connection attempts.

#### Example of `connection_history.json`:
```json
{
    "owner_address": "0x142B9B25BC3D5AcDd02D81d2d77Efcba6A2892f5",
    "total_rewards": 15.419999999999998,
    "connection_history": [
        "RPC Connection (ID: RPC_20250428074310_b957fa) - Failed",
        "Node Request (ID: NODE_20250428074310_76161a) - Success: 0.16 VaultChain Tokens",
        "Peer Connection (ID: PEER_20250428074310_b324f8) - Failed",
        "Beacon Chain Connection (ID: BEACON_20250428074310_fbd6b1) - Success: 0.28 VaultChain Tokens",
        "Mainnet Connection (ID: MAINNET_20250428074310_f705f4) - Failed",
        "RPC Connection (ID: RPC_20250428074312_be1890) - Failed",
        "Node Request (ID: NODE_20250428074312_d1109e) - Success: 0.35 VaultChain Tokens"
    ]
}
```

Connection logs provide detailed insights into network connectivity issues, helping to diagnose problems with node synchronization, network peers, or any communication failures.

---

## VaultChain Mainnet Stability

### Maintaining Validator Stability
Validator node stability is crucial to the overall health of the VaultChain network. The following components are essential to ensuring that validators are performing optimally:

1. **Validator Rewards**: Each validator node earns rewards by validating blocks on the VaultChain Mainnet. These rewards are recorded in the **`validator_log.json`** file and tracked over time.
   
2. **Syncing Status**: The status of the node's synchronization with the VaultChain network should be monitored regularly. Logs track the state of the node (`Syncing`, `Connected`, `Failed`), which helps in identifying syncing problems early on.

3. **Error Monitoring**: Connection errors or validation failures should be addressed quickly to ensure the continued operation of the node. Logs should be checked regularly for any warnings or errors.

### Maintaining Network Stability
For the VaultChain network to remain stable and scalable, the following principles are critical:

1. **Peer Connections**: The number of peers connected to each node directly impacts its ability to validate transactions and blocks efficiently. Connection logs monitor successful and failed peer connections.

2. **Mainnet Connectivity**: Stable and secure connections to the mainnet (including RPC and Beacon Chain) are essential for the operation of any VaultChain node. Connection logs help in monitoring the health of these network connections.

3. **Security and Monitoring**: Frequent monitoring of the validator and connection logs ensures that any issues (such as failed connections or downtime) are identified early. Regular updates and bug fixes for the VaultChain node software are recommended to address any security vulnerabilities.

---

## Starting the VaultChain Validator Node

To start a VaultChain Validator node and contribute to the Mainnet, follow these steps:

1. **Install Dependencies**: Ensure that all necessary dependencies are installed for running the VaultChain node (e.g., Python, PyQt6, etc.).
   
2. **Run the Validator Node**:
   - Execute the VaultChain validator software to begin the synchronization and validation process.
   - Monitor the logs to track the node's performance and reward earnings.

3. **Check Logs**: Use the **`validator_log.json`** and **`connection_history.json`** files to monitor your validator's activity and network connectivity status.

---

## License

VaultChain Network code and tools are distributed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html).