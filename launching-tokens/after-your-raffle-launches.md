# After Your Raffle Launches

Once deployed, your raffle runs automatically. Here's what happens next.

## During the Raffle

- Winners are drawn at your configured draw frequency (e.g., every 1 second).
- The minting progress bar shows how many raffle tokens have been distributed out of the total raffle pool.
- You can monitor participation from the raffle detail page: recent winners, leaderboard of top ticket buyers, and live stats.

## Raffle Completion

The raffle ends when either:
- **All raffle tokens are distributed** (sold out), or
- **The expiry time is reached** (remaining tokens are burned)

## Liquidity Migration and DAO Sovereignty

After the raffle ends, liquidity migrates automatically and the DAO takes full ownership:

1. The remaining 50% of token supply is paired with collected APT.
2. A liquidity pool is created on the configured DEX (Tapp DEX).
3. **Token admin rights** (mint, burn, transfer) are transferred to the DAO account.
4. **LP tokens** are transferred to the DAO account.
5. **External access to the DAO is killed** — no wallet, including the creator's, can control the DAO directly.

The raffle page shows migration status in real-time. Once complete, a green banner appears with an **Open Swap** link to trade the token.

After migration, the creator has no special privileges. All control flows through governance — proposals and votes, same as every other token holder.

## Your Token's DAO

Every launched token gets a fully sovereign DAO. As a token holder, you can:

- Create governance proposals (requires 100+ tokens)
- Vote on proposals from other holders
- Execute passed proposals (any wallet can do this — just pays gas)
- Manage LP positions, treasury funds, token supply, and metadata through governance

The DAO account is the treasury. All assets (APT, tokens, LP positions) live at the DAO address and can only be moved through passed proposals.

See the [Governance](../governance/how-governance-works.md) section for details.
