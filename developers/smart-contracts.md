# Smart Contracts

Sudo Protocol is built on two core Move modules deployed on the Aptos blockchain.

## Modules

### sudo\_fa.move — Fungible Asset Token

Handles token creation and lifecycle management using the Aptos Fungible Asset (FA) standard.

**Capabilities:**

* Token initialization with name, symbol, decimals, icon URI, and project URI
* Mint, burn, and transfer operations
* Creator-controlled token management via stored refs (MintRef, BurnRef, TransferRef)
* View functions for metadata lookup and balance queries

### sudo\_raffle.move — VRF Raffle Engine

Manages the fair-launch raffle mechanism for token distribution.

**Capabilities:**

* Raffle state management (active, completed, expired)
* Ticket purchase with configurable pricing (paid or free)
* Winner selection via `aptos_framework::randomness::u64_range()` with the `#[randomness]` attribute — native Aptos on-chain VRF
* Vault system for secure token and APT management
* Configurable draw frequency and raffle expiry
* User participation tracking and history
* Event emission for off-chain indexing

## On-Chain Randomness

Winner selection uses Aptos native VRF. The `#[randomness]` attribute on the raffle function ensures the random seed is derived from the validator set and is unpredictable before the block is finalized. No external oracle (Chainlink VRF, Switchboard) is needed.

```move
use aptos_framework::randomness;

#[randomness]
entry fun execute_raffle(...) {
    let winner_index = randomness::u64_range(0, vector::length(&state.buyers));
    // ...
}
```

## Token Distribution Model

Every token launch splits the supply 50/50:

* **50% Raffle Pool** — Distributed to raffle winners via VRF
* **50% Liquidity** — Paired with collected APT and migrated to DEX after raffle completion

The resulting LP position is owned by the token's DAO.

## Governance

Each token's DAO supports on-chain governance with proposals and voting. Governance actions include LP management (lock, migrate, rebalance), token minting/burning, metadata updates, and key management.

Permissionless proposal execution via SignerCapability is in development — see [GitHub issue #4](https://github.com/Sudo-Protocol/sudo-latest/issues/4) for the full design.

## Source Code

GitHub: [Sudo-Protocol/sudo-latest](https://github.com/Sudo-Protocol/sudo-latest)
