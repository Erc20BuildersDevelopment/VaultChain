# VaultChain Staking Mechanism

Welcome to the **VaultChain** staking guide. This document provides a comprehensive overview of how staking works in the VaultChain blockchain, including how to become a Validator, stake tokens, and understand the directory structure for each staker.

---

## 🚀 Overview

VaultChain introduces a decentralized staking system that allows users to become **Validators** and earn rewards for securing the network. Validators play a crucial role in block production, validation, and consensus within the VaultChain ecosystem.

To participate, users must meet certain staking requirements and follow a structured setup process.

---

## 🧾 Staking Requirements

To become a Validator and stake on the VaultChain network, users must provide the following:

### ✅ **Mandatory Requirements**
- **200 VaultChain Tokens (VTK):**  
  Minimum staking amount required to become eligible as a Validator.  
  ➤ _Can be obtained via the VaultChain daemon or from a Validator node._

- **0.05 sETH (Staking Ethereum):**  
  A small amount of sETH is required to activate the Validator and perform staking operations.

### 🔁 **Optional (Bonus)**
- **0.1 sETH (Boosted Rewards):**  
  If supplied, this additional amount allows the Validator to receive **multiplied rewards** based on staking performance and uptime.

---

## 🏗️ Staker Directory Structure

Each Validator is represented by a unique staking folder, named using the following convention:

```
stake_xx/
```

Where `xx` is a unique numeric or alphanumeric identifier.

Each `stake_xx` folder contains:

| File Name        | Description |
|------------------|-------------|
| `address.stk`     | Stores the Validator’s Ethereum-compatible address (viewable on [Etherscan](https://etherscan.io/)) |
| `build.json`      | Contains core staking metadata such as token amount, sETH contributed, optional bonuses, start timestamp, validator ID, and status |
| `hashes.json`     | Contains cryptographic hashes used for verifying Validator signatures, checkpoint hashes, and stake integrity |

### 📁 Example

```
stake_12/
├── address.stk        # 0x1234...abcd
├── build.json         # staking metadata
├── hashes.json        # cryptographic verifications
```

---

## 📜 build.json Format

Below is an example of what `build.json` might look like:

```json
{
  "validator_id": "validator_12",
  "vtk_staked": 200,
  "sETH_committed": 0.05,
  "sETH_optional": 0.1,
  "reward_multiplier": true,
  "stake_status": "active",
  "start_time": "YY-MM-DD  HH:MM.SS",
}
```

---

## 🔐 hashes.json Format

Example of the cryptographic data stored in `hashes.json`:

```json
{
  "stake_signature": "0xabcdef123456...",
  "checkpoint_hash": "0xdeadbeef7890...",
  "integrity_proof": "0xfeedfacecafebabe..."
}
```

These are used by the VaultChain consensus mechanism to verify the authenticity of each stake and Validator activity.

---

## ⚙️ How to Stake

1. **Ensure you have:**
   - ≥ 200 VTK in your wallet
   - ≥ 0.05 sETH (plus 0.1 sETH optionally)

2. **Run the VaultChain Staking CLI or Daemon:**
   ```bash
   vaultchain stake --vtk 200 --sETH 0.05 --boosted
   ```

3. **Validator Folder is Created:**
   - A new `stake_xx/` folder will appear in `network/staking/`
   - All relevant files (`address.stk`, `build.json`, `hashes.json`) are generated

4. **Start Validating:**
   - Your node is now active in the network
   - Earn staking rewards based on performance and time

---

## 🏆 Rewards

Validators receive rewards based on:
- Uptime
- Participation in consensus
- Bonus multiplier if optional sETH was staked

Rewards are paid in **VTK** periodically and logged into the Validator’s wallet address.

---

## 🛑 Unstaking

To stop staking:
```bash
vaultchain unstake --validator validator_12
```

This will:
- Deactivate the Validator
- Initiate a cooldown period
- Return staked VTK and sETH to your wallet after verification

---

## 🧠 Notes

- All Validator actions are on-chain and auditable.
- Make sure your node is always online to maximize rewards.
- Validators with inactivity may be penalized or slashed based on protocol rules.

---

## 📫 Support

For questions or troubleshooting:
- Join our [Discord](https://discord.gg/vaultchain)
- Submit issues via [GitHub Issues](https://github.com/VaultChain/issues)

---

## 🔗 Related

- [VaultChain Daemon Setup](../daemon/README.md)
- [VaultChain Validator Node Guide](../validator/README.md)
