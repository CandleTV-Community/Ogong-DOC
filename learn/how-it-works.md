# How it works

The network has three roles, and one person can run any or all of them.

**Providers** are the GPUs. They run the models and serve your request, and becoming one is just turning on the software, with no money at risk.

**Routers** match your request to a good provider and pass it along quickly. A router runs inside a sealed hardware enclave (a "trusted execution environment"), so it executes code it can prove to you, and that code cannot read the prompt passing through it. You can check the proof before trusting it.

**Validators** are the referees, and they don't need a GPU. They run the random audit lottery, hand suspicious requests to a checker, and record the verdicts. They're the only role that posts a financial stake, and only as a penalty for lying about a verdict.

Here's the path a request takes:

1. **You send it.** Your prompt is encrypted so only the chosen provider can open it.
2. **A router matches you to a provider** based on price, speed, and the provider's track record. The cheapest doesn't automatically win, because audit history counts toward the score.
3. **The provider answers** and, alongside the answer, publishes a small cryptographic "receipt" of the computation it did, just a few hundred bytes.
4. **Your fee sits in escrow** and isn't released yet.
5. **The audit lottery runs.** The request might be selected for checking at random, and the provider can't tell in advance whether it's being watched, so the only safe strategy is to always run the real model.
6. **If selected, a different provider re-checks the receipt** at a tiny fraction of the original cost. If it matches, the fee is released. If it doesn't, the fee is withheld, refunded to you, and the cheater gets flagged.

The reason this works is that checking a request is far cheaper than running it. The check is a single fast pass over the finished answer, up to 100 times cheaper than generating it, which works out to somewhere between 1 and 5 percent of the original cost depending on the hardware. Because checking is so cheap, Ogong can audit almost everything instead of spot-checking a small sample, and once nearly every request is checked, cheating stops paying off on the very first attempt.
