# Creating a Raffle

Anyone can launch a token on Sudo. The platform handles smart contract deployment, raffle mechanics, and liquidity migration automatically.

## Quick Deploy

Click the **Quick Deploy** button at the top of the create page to launch with sensible defaults. This fills in all fields and starts deployment immediately.

## Step-by-Step Setup

Navigate to **Create Raffle** from the top menu.

### Token Details

| Field | Description | Example |
|---|---|---|
| **Raffle Title** | Name for your raffle (max 100 characters) | "Community Token Launch" |
| **Description** | What makes your token or raffle special | "Fair launch for our community governance token" |
| **Symbol** | Token ticker, 2-10 uppercase letters/numbers | "SUDO" |
| **Token Logo** | Optional 512x512 PNG or SVG | — |

### Raffle Parameters

| Field | Description | Example |
|---|---|---|
| **Ticket Price** | APT per ticket. Set to 0 for a free raffle. | 0.01 APT |
| **Winning Ticket** | Number of tokens each winner receives | 10 |
| **Total Supply** | Total token supply (minimum 1,000) | 1,000,000 |
| **Draw Frequency** | How often a winner is drawn | Every 1 second |
| **Raffle Expiry** | How long the raffle runs before unsold tokens are burned | 24 hours |
| **DEX Platform** | Where liquidity will be created after the raffle | Tapp DEX |

### Free Raffle: Initial Liquidity

If ticket price is 0, a free raffle doesn't collect APT from buyers. You'll need to seed the initial DEX liquidity yourself.

An **Initial Liquidity (APT)** field appears when the ticket price is set to 0. Enter the amount of APT you want to pair with tokens in the liquidity pool. The estimated starting token price is calculated and displayed.

### DAO Settings

Every raffle creates a DAO for its token. You can configure:

| Field | Default | Description |
|---|---|---|
| **Proposal Quorum** | 10% | Minimum % of voting power needed for a proposal to pass |
| **Proposal Duration** | 7 days | How long proposals stay open for voting |

### Raffle Rules

Custom rules displayed to participants. Two defaults are pre-filled:

1. "There is always 1 winner every lottery"
2. "The Raffle lasts until all tokens are distributed"

You can add, edit, or remove rules.

## Deploying

1. Click **Deploy Raffle**.
2. The platform validates your form and uploads metadata to IPFS.
3. A deployment stepper modal appears with two steps:
   - **Deploy Complete System** — Creates your token and raffle contracts on-chain.
   - **Initialize Raffle** — Sets up the raffle state. You'll sign a transaction (gas only).
4. For free raffles: you'll sign one additional transaction to seed the initial APT liquidity.
5. Once complete, your raffle is live and visible on the home page.

## Token Distribution

Every token launch splits the supply:

- **50% Raffle Pool** — Distributed to raffle winners
- **50% Liquidity** — Paired with collected APT (or creator-seeded APT for free raffles) and migrated to the DEX

The DAO owns the resulting liquidity pool position.
