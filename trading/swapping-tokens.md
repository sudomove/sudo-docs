# Swapping Tokens

After a raffle completes and liquidity migrates to the DEX, you can trade that token directly on Sudo.

## How to Swap

1. Navigate to **Swap** from the top menu.
2. Select a token from the list on the left. Tokens with migrated liquidity are shown first.
3. Choose your direction: **Buy** (APT to token) or **Sell** (token to APT).
4. Enter the amount you want to swap.
5. Review the estimated output, price impact, and minimum received.
6. Click **Swap** and sign the transaction in your wallet.

## Token List

The swap page shows all tokens that have been launched on Sudo. Tokens are sorted with completed (migrated) tokens first. You can search by name or symbol.

Each token shows:
- Symbol and name
- Your balance (if you hold any)
- APT value equivalent
- Migration status (Migrated or Pending)

Only tokens with a **Migrated** status have an active liquidity pool and are tradeable.

## Swap Details

Before confirming, the swap widget shows:

- **Estimated output** — How many tokens (or APT) you'll receive
- **Price impact** — How much your trade moves the pool price
- **Current spot price** — The current exchange rate
- **Pool reserves** — How much APT and token are in the pool

## Slippage Settings

Click the settings icon to adjust slippage tolerance (default: 1%). This sets the minimum amount you'll accept. If the price moves more than your slippage tolerance between submission and execution, the transaction reverts.

## Requirements

- Wallet connected
- Sufficient balance of the input token (APT or the traded token)
- The token must have a live liquidity pool (status: Migrated)
