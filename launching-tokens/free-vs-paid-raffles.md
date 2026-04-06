# Free vs. Paid Raffles

Sudo supports both free and paid token raffles. The choice affects how liquidity is funded.

## Paid Raffles

- Users pay APT per ticket (e.g., 0.01 APT).
- The APT collected from ticket sales funds the DEX liquidity pool.
- After the raffle ends, 50% of the token supply + all collected APT migrate to the DEX as a liquidity pair.
- The DAO owns the LP position.

**Best for:** Projects that want price discovery driven by participant demand.

## Free Raffles

- Tickets cost 0 APT (users only pay gas).
- Since no APT is collected, the creator seeds the liquidity pool with their own APT.
- An **Initial Liquidity** field appears during raffle creation where the creator specifies how much APT to contribute.
- The creator signs an additional transaction during deployment to transfer the APT.

**Best for:** Community airdrops, promotional launches, or projects that want maximum participation.

## What Happens If a Raffle Expires

If a raffle reaches its expiry time before all tickets are sold:

- Distributed tokens stay with winners.
- Remaining unsold tokens are burned proportionally.
- Whatever APT was collected (or seeded) still migrates to the DEX with the distributed tokens.
- The raffle page shows how many tokens were distributed vs. burned.
