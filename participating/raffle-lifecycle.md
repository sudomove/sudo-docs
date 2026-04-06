# Raffle Lifecycle

Every raffle on Sudo moves through a series of states from creation to completion.

## States

### 1. Upcoming

The raffle has been created but hasn't started yet. A countdown shows time until it goes live. You can view the raffle details but can't buy tickets.

### 2. Live

The raffle is active. Users can buy tickets. Winners are drawn automatically at the configured draw frequency using Aptos on-chain VRF.

The raffle detail page shows:
- Minting progress bar (tokens distributed / total raffle pool)
- Recent winners in the block feed
- Leaderboard of top ticket buyers
- Countdown to expiry (if set)

### 3. Sold Out

All raffle pool tokens have been distributed. No more tickets can be purchased. The raffle transitions to liquidity migration.

### 4. Expired

The raffle reached its expiry time before all tokens were sold. When this happens:
- Tokens already distributed stay with winners.
- Remaining unsold raffle tokens are burned proportionally.
- The raffle page shows the split: "X distributed / Y burned."

### 5. Migrating

Liquidity is being created on the DEX. This happens automatically after a raffle sells out or expires:
- Token supply (50% liquidity allocation) and collected APT are paired.
- The liquidity pool is created on the configured DEX (Tapp DEX).
- A progress indicator shows migration status in real-time.

### 6. Migrated

Liquidity migration is complete. The token is now tradeable on the DEX. The raffle page shows a green banner with an **Open Swap** button linking to the swap page for that token.

### 7. Migration Failed

Rare — if liquidity migration encounters an error, a red banner is displayed. The team may need to investigate or retry.

## Visual Summary

```
Upcoming  -->  Live  -->  Sold Out  -->  Migrating  -->  Migrated
                 |
                 +--->  Expired  --->  Migrating  -->  Migrated
```
