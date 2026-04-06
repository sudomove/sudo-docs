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

## Liquidity Migration

After the raffle ends, liquidity migrates automatically to the configured DEX (Tapp DEX):

1. The remaining 50% of token supply is paired with collected APT.
2. A liquidity pool is created on the DEX.
3. The LP position is owned by the token's DAO.

The raffle page shows migration status in real-time. Once complete, a green banner appears with an **Open Swap** link to trade the token.

## Your Token's DAO

Every launched token gets a DAO. As the creator and a token holder, you can:

- Create governance proposals
- Vote on proposals from other holders
- Manage LP positions, token supply, metadata, and more through governance

See the [Governance](../governance/how-governance-works.md) section for details.
