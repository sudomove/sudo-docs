# Creating a Proposal

Any token holder with at least 1 winning ticket worth of tokens can create a governance proposal for their token's DAO. The threshold equals the raffle's "Winning Ticket" amount — the same number of tokens a single raffle winner receives.

## Steps

1. Go to **Governance** and select a DAO.
2. Click **Create Proposal**.
3. Follow the four-step form:

### Step 1: Choose Action Type

Select what your proposal does:

- **Manage LP Tokens** — Lock, migrate, or rebalance the DAO's liquidity position
- **Mint Tokens** — Create new tokens and send them to an address
- **Burn Tokens** — Burn tokens from an address
- **Update Token Metadata** — Change the token's name, symbol, URI, or description
- **Transfer Funds** — Send APT or tokens from the DAO treasury

### Step 2: Configure the Action

Depending on your action type:

**Manage LP Tokens:**
- Select the DEX venue
- Choose an LP action:
  - **Lock** — Lock LP tokens for a specified duration (in days)
  - **Migrate** — Move liquidity to a different DEX
  - **Rebalance** — Remove some or all liquidity, optionally re-add at different ratios. Removed funds go to the DAO treasury.

**Mint Tokens:**
- Enter the amount to mint
- Enter the destination wallet address

**Burn Tokens:**
- Enter the amount to burn
- Enter the source wallet address

**Update Token Metadata:**
- Check which fields to update (name, symbol, URI, description)
- Fill in the new values for checked fields

**Transfer Funds:**
- Select the asset (APT or token)
- Enter the amount
- Enter the destination wallet address

### Step 3: Set Voting Parameters

- **Proposal Title** — A clear, descriptive title
- **Description** — Explain what you're proposing and why
- **Voting Start** — Start now or schedule for a future date
- **Voting Duration** — How many days the vote stays open (default: 7)
- **Quorum %** — Minimum voting participation required (default: 20%)
- **Pass Threshold %** — Percentage of yes votes needed to pass (default: 50%)

### Step 4: Review and Submit

Review all parameters and click **Submit Proposal**. Sign the transaction in your wallet to create the proposal on-chain.

## Requirements

- Hold at least **1 winning ticket worth of tokens** to create a proposal.
- Wallet must be connected.

## After Submission

Your proposal appears in the DAO's proposal list with an **Active** status badge. Other token holders can now vote on it for the duration you configured.

Once the proposal passes and the voting period ends, anyone can execute it — see [Voting](voting.md) for details on execution.
