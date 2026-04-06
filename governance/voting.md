# Voting

Any token holder can vote on active governance proposals in their DAO.

## How to Vote

1. Go to **Governance** and select a DAO where you hold tokens.
2. Click on an active proposal to open the detail view.
3. Review the proposal title, description, and action details.
4. Click **Yes** or **No** to cast your vote.
5. Sign the transaction in your wallet.

## Voting Power

Your voting power equals your token balance. 1 token = 1 vote. The more tokens you hold, the more weight your vote carries.

Your current voting power is displayed in the DAO detail page header and in the **Powers** tab.

## Proposal Lifecycle

| Status | Meaning |
|---|---|
| **Active** | Voting is open — you can cast your vote |
| **Passed** | Voting ended, quorum and threshold met — ready for execution |
| **Executed** | Proposal was executed on-chain |
| **Failed** | Proposal didn't reach quorum or pass threshold |

## Executing a Passed Proposal

Once a proposal reaches **Passed** status (voting period ended, quorum met, pass threshold met), anyone can execute it:

1. Open the passed proposal.
2. Click **Execute Proposal**.
3. Sign the transaction — you just pay gas.

Execution is fully permissionless. You don't need to be the proposer, a token holder, or an admin. The governance contract validates that the proposal passed legitimately, then uses the DAO's stored SignerCapability to carry out the approved action. The caller has no influence over what gets executed — they only trigger what was already voted on.

## Quorum and Pass Threshold

Every proposal has two requirements to pass:

- **Quorum** — Minimum percentage of total voting power that must participate (default: 10-20%). If not enough people vote, the proposal fails regardless of the yes/no split.
- **Pass Threshold** — Minimum percentage of votes that must be "yes" (default: 50%). If quorum is met but not enough yes votes, the proposal fails.

Both values are displayed on the proposal detail view along with a progress bar showing current participation vs. required quorum.

## Real-Time Updates

Vote counts update in real-time via live connection. As other holders vote, you'll see the vote bar and quorum progress update instantly. Toast notifications appear when new votes are cast.

## One Vote Per Wallet

Each wallet address can vote once per proposal. You cannot change your vote after casting it.

## Security

- **No double execution** — A proposal can only be executed once. The contract marks it as executed atomically before dispatching the action.
- **No admin override** — The DAO account has a dead authentication key. No external wallet can sign transactions as the DAO.
- **Slippage protection** — LP operations include minimum output amounts. If the pool moves too much between proposal creation and execution, the transaction reverts.
- **All on-chain** — Every proposal, vote, and execution is recorded on-chain and publicly verifiable.
