# How Governance Works

Every token launched on Sudo automatically gets a sovereign DAO. After the raffle completes and liquidity migrates, all token admin rights and LP tokens are transferred to the DAO. No admin retains any control. The DAO is the sole owner from that point forward.

## The Basics

- **Voting power** is based on your token balance. 1 token = 1 vote.
- **Anyone holding at least 1 winning ticket worth of tokens** can create a proposal. The threshold equals the raffle's "Winning Ticket" amount — the same number of tokens a single winner receives.
- **Anyone with voting power** can vote on active proposals.
- **Execution is fully permissionless** — once a proposal passes, any wallet can trigger execution. You just pay gas. No admin key, no operator, no single point of failure.

## DAO Sovereignty

When a raffle completes and liquidity is migrated, the following happens automatically:

1. **Token admin rights** (mint, burn, transfer) are transferred to the DAO account.
2. **LP tokens** are transferred to the DAO account.
3. **External access is killed** — the DAO account's authentication key is rotated to a dead key. No wallet can sign transactions as the DAO.
4. **All fund movement requires a passed proposal** — the DAO uses a stored SignerCapability that can only be invoked inside the governance contract's `execute_proposal` function.

The DAO account address IS the treasury. APT, tokens, and LP positions all live there. The creator retains nothing after migration.

## What Can Be Governed

DAOs on Sudo can make proposals across these categories:

| Action | What It Does |
|---|---|
| **LP Rebalance** | Remove liquidity, re-add with different ratios, or hold as treasury |
| **LP Migrate** | Move liquidity from one DEX to another |
| **LP Lock** | Lock the LP position for a specified duration |
| **Mint Tokens** | Mint new tokens to a specified address |
| **Burn Tokens** | Burn tokens from a specified address |
| **Update Token Metadata** | Change the token's name, symbol, URI, or description |
| **Transfer Funds** | Send APT or tokens from the DAO treasury to an address |
| **Signal Proposal** | Non-binding text proposal for community sentiment |

## Permissionless Execution

Once a proposal passes (meets quorum and pass threshold) and the voting period ends, **anyone** can call `execute_proposal`. The caller just pays gas — they have zero authority over the DAO. The governance contract uses the stored SignerCapability to execute the approved action on behalf of the DAO.

This means:
- No admin can block a passed proposal
- No single point of failure for execution
- Any community member (or bot) can trigger execution
- The caller cannot modify, redirect, or alter the proposal — they only trigger what was already approved

## DAO Parameters

Each DAO has configurable governance parameters set at launch:

- **Proposal Quorum** — Minimum percentage of voting power that must vote for a proposal to be valid (default: 10%).
- **Proposal Duration** — How long a proposal stays open for voting (default: 7 days).

## Accessing Governance

Navigate to **Governance** from the top menu to see:
- **All DAOs** — Every DAO on the platform
- **My DAOs** — DAOs where you hold tokens (requires wallet connection)
- **Stats** — Total DAOs, your DAOs, active proposals, total proposals

Click a DAO to view its proposals, voting power breakdown, and governance rules.
