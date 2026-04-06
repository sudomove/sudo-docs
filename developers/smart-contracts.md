# Smart Contracts

Sudo Protocol is built on core Move modules deployed on the Aptos blockchain.

## Modules

### sudo\_fa.move — Fungible Asset Token

Handles token creation and lifecycle management using the Aptos Fungible Asset (FA) standard.

**Capabilities:**

* Token initialization with name, symbol, decimals, icon URI, and project URI
* Mint, burn, and transfer operations
* Token admin rights stored in a transferable Object (MintRef, BurnRef, TransferRef)
* Admin Object transferred to DAO account after liquidity migration
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

## Governance — Permissionless Execution

Each token's DAO supports fully permissionless on-chain governance.

**Architecture:**

* DAO account is created as a resource account with a stored `SignerCapability`
* External access is killed via dead authentication key (zero key + dead authenticator)
* Token admin Object and LP tokens are transferred to the DAO after migration
* `execute_proposal()` is callable by any wallet — the caller just pays gas
* The SignerCapability is only accessible inside the governance module's execution function — it cannot be used for arbitrary transactions

**Governance actions:** LP rebalance, LP migrate, LP lock, mint, burn, metadata updates, treasury transfers, signal proposals.

**Security properties:**

* No admin retains any control after migration
* Proposals can only be executed once (atomic `executed` flag set before dispatch)
* LP operations include slippage protection (reverts if pool moved too much)
* All proposals, votes, and executions are on-chain and publicly verifiable

## Source Code

GitHub: [Sudo-Protocol/sudo-latest](https://github.com/Sudo-Protocol/sudo-latest)
