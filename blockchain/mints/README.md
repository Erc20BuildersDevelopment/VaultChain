# `blockchain/mints`

The `blockchain/mints` directory serves as the **minting database path** for the VaultChain Blockchain. It contains a record of all minting events that have occurred on the blockchain, with each event stored as a separate JSON object.

## Purpose

This directory acts as a ledger for mint transactions, ensuring transparency and traceability of all token minting events. Every file (or entry) represents a single minting operation tied to a specific block in the chain.

## JSON Structure

Each mint record is stored in JSON format, using the following schema:

```json
{
  "Block_ID": "string",             // Unique identifier of the block where the mint occurred
  "owner_address": "string",        // Wallet address of the entity that minted the tokens
  "Tokens_Minted": integer,         // Number of tokens minted in this transaction
  "Mined": true | false             // Whether the minting has been mined (confirmed on-chain)
}
```

### Example

```json
{
  "Block_ID": "000000abc123",
  "owner_address": "0x1a2b3c4d5e6f7890",
  "Tokens_Minted": 1000,
  "Mined": true
}
```

## Usage

- New mint records should be appended in this directory after mint transactions are initiated.
- Each file may be named using the `Block_ID`, timestamp, or transaction hash to ensure uniqueness.
- The `Mined` flag allows for asynchronous confirmation tracking — it is set to `false` initially and updated to `true` once the transaction is confirmed on-chain.

## Notes

- This path is integral to the minting workflow in VaultChain. Do **not** manually edit files unless performing maintenance or recovery with consensus approval.
- The system reading this directory expects valid JSON. Malformed records may disrupt the integrity of mint logs.