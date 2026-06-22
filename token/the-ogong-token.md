# The OGONG token

OGONG is the network's settlement currency. Providers, routers, and validators are paid in it, and it's what you spend to run inference, though a card gateway can handle that for you so you never have to hold it yourself. The same token is also the validator's slashable bond, the provider's priority stake, and the governance vote over network parameters like the model catalog and the audit settings.

Supply is capped at 1 billion tokens, with no inflation past the cap and no token burning. Most of it is earned rather than handed out, and the value of the token is meant to come from real usage of the network against that fixed supply.

## Allocation

| Bucket | Share | Tokens | Notes |
|---|---|---|---|
| Earned emissions | 80% | 800M | Mined over roughly 20 years for verified work and uptime, by providers, validators, and routers |
| Public liquidity | 2.5% | 25M | Launch liquidity through a bonding curve that migrates to a public market (2%), plus a reserve for exchange listings (0.5%) |
| Core team & advisors | 12.5% | 125M | Vested on a wall-clock schedule, with no control rights |
| Foundation | 5% | 50M | Independent steward with a public on-chain budget, no founder control |

The launch-liquidity proceeds are locked into the market rather than taken by the team or the company, and the team and Foundation allocations vest over time and carry no control over the protocol.

## How tokens are earned

The 80 percent earned tranche is never pre-allocated. It's released gradually on a Bitcoin-style halving schedule over roughly two decades, and the only way to receive it is to do work the network can verify: serving real inference that passes the audit, checking other providers' work, or routing requests correctly. There's also a smaller reward for being online and ready to serve, which lets a fresh node start earning before traffic reaches it. Both are checked the same way an ordinary request is, so faking uptime fails exactly like faking a result. Turning your machine on and serving honestly is the whole path to new supply.

## Where the fees go

When a request is paid for, the fee is split among the parties that produced the service: most of it to the provider that ran the model, a slice to the router and to the validator that settled the payment, a small reserve for verification, and a small protocol cut that funds an on-chain treasury spent by governance. There's no dividend or revenue share paid out to people who simply hold the token.

## What it is, and what it isn't

Staking OGONG buys priority, which means more routing weight and so more work and more earnings. It's a position in the queue rather than interest on a deposit. The token is designed as the network's settlement and utility asset, not as an investment product, and most end users never touch it because the fiat gateway settles on their behalf. It launches as a capped-supply token on Solana and is built to move to its own dedicated chain later through a standard bridge.
