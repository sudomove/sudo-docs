# Creating a Proposal

Any token holder with at least 100 tokens can create a governance proposal for their token's DAO.

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
- **Change DAO Keys** — Add, remove, or rotate governance keys

### Step 2: Configure the Action

Depending on your action type:

**Manage LP Tokens:**
- Select the DEX venue
- Choose an LP action: Lock (set duration in days), Migrate (choose destination DEX), or Rebalance

**Mint Tokens:**
- Enter the amount to mint
- Enter the destination wallet address

**Burn Tokens:**
- Enter the amount to burn
- Enter the source wallet address

**Update Token Metadata:**
- Check which fields to update (name, symbol, URI, description)
- Fill in the new values for checked fields

**Change DAO Keys:**
- Choose the key action (add, remove, or rotate)
- Enter the key address

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

- Hold at least **100 tokens** in the DAO to create a proposal.
- Wallet must be connected.

## After Submission

Your proposal appears in the DAO's proposal list with an **Active** status badge. Other token holders can now vote on it for the duration you configured.

## Current Limitations

Governance is currently in its first phase. Proposals and voting are fully on-chain, but proposal execution is not yet permissionless — passed proposals are executed through a governance key. Full permissionless execution via SignerCapability (where any wallet can trigger execution of passed proposals) is being implemented in the next upgrade. See [GitHub issue #4](https://github.com/Sudo-Protocol/sudo-latest/issues/4) for the full design.
