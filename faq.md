# FAQ

**Is Ogong actually live?**
The protocol and its full audited path are built and measured in a reference implementation, with the verification, the privacy sealing, and the settlement all running end to end. Growing that into a large, open network with many independent operators is the next phase. We're specific about this: a real network starts from a small operator set and decentralizes from there, and we don't claim to be more decentralized than we are at any given moment.

**Do I need crypto to use it?**
No. You can pay by card through a gateway that handles the token for you. Holding OGONG is optional, and mainly matters if you run a node or want priority.

**How is this private if it's on a blockchain?**
The AI never runs on the blockchain, which would be far too slow and wasteful. The chain only records small bits of metadata like payments and audit verdicts. Your actual prompt is encrypted and travels off-chain straight to the provider, so the chain never sees its content.

**What stops a provider from cheating with a cheaper model?**
Nearly every request is cheaply audited, and the audit checks the model's internal computation, which is as hard to fake as running the real model. Cheating gets caught on the first try and the provider loses the fee, so there's no profitable way to do it.

**Can the people running the network see what I'm asking?**
On the TEE tier, no. The hardware is blind to your prompt and you can verify that. On the public tier the provider can see it, but this is clearly labeled so it's never a surprise.

**What makes this different from other private or decentralized AI?**
Two things, both checkable rather than promised. Your prompt is sealed so the operator can't read it, and on the TEE tier you can verify that instead of trusting a no-logging policy. On top of that, and unique to Ogong, the network proves on nearly every request that the model you paid for is the one that actually ran. Routing a prompt privately is one thing; proving which model answered is another, and that's the part Ogong adds.
