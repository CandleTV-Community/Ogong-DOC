# Ogong

**Private AI you don't have to trust.**

Ogong is a decentralized network for running AI models on hardware you don't own. Whoever owns the machine that answers your request can't read what you send, and the network can prove you got the model you paid for instead of a cheaper substitute.

Most "decentralized AI" projects run on a promise: we don't log your prompts, we run the real model. Ogong replaces that promise with a mechanism. Privacy is enforced by the hardware and the cryptography rather than by an operator's word, and correctness is checked on nearly every request by an audit layer that catches a provider swapping in a weaker model. You don't have to trust anyone. The protocol does the checking.

## What is Ogong

Ogong is an open, permissionless network with a few simple properties:

- **Anyone with a GPU can serve AI** and get paid for it. Turning your machine on is the whole signup, with no application and no capital to lock up.
- **Anyone can use it** through a standard OpenAI-compatible API or a chat app. You pay a small fee per request, and you can pay by card without ever touching crypto.
- **The network checks the work.** Any request can be audited to confirm the provider really ran the model it claimed, at the quality it claimed.
- **Your prompt stays private.** It's encrypted to the provider that answers it, and the machines in between only relay sealed data they can't open.

The name comes from Ogong (오공), the Monkey King, who sees through any disguise with his golden eyes. The audit layer that catches providers in a lie is called **Golden Eyes**.

Put simply, Ogong is the privacy and verification layer that lets you buy AI from strangers without trusting any of them.

---

*This documentation is a plain-English companion to the Ogong technical paper. For the formal mechanism design, proofs, and measurements, see the paper.*
