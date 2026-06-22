# Verified, not promised

This is what sets Ogong apart, and it comes down to two guarantees, both enforced by mechanism.

## Privacy: the operator can't read your prompt

Your request is sealed with encryption that only the provider answering it can open, and that encryption is built to survive future quantum computers. The router in the middle relays sealed bytes it has no key for, and because it runs as attested code inside a hardware enclave, you can verify it's running honest software before you send anything.

The chain (the public ledger) only ever sees metadata, like who paid for which model and when. It never sees the content of your prompt, which stays off it entirely.

Ogong offers two tiers and labels them clearly:

- **TEE tier:** full hardware-enforced confidentiality, where the machine running your inference is mathematically blind to your prompt. This is the strongest setting.
- **Public tier:** the provider can see the prompt, which is always labeled and never hidden, but correctness is still checked by audit. This is the cheaper option.

You always know which one you're getting. There's no "private by default" marketing that quietly means "we promise not to look."

## Correctness: the network proves the right model ran

This is the guarantee that's hardest to find elsewhere. When a provider answers, it commits to a fingerprint of the model's internal state as it generated each piece of the output, and a checker re-runs a sliver of that and compares.

The gap this exposes is wide. An honest provider's output lines up with the real model essentially 100 percent of the time, while a cheaper model from a different family lines up only about half the time, an obvious tell. The subtler cases, a same-family model one size down or the same model quietly run at lower precision, can slip past a glance at the output but stand out clearly in the activations, which is exactly where the internal fingerprint earns its keep. In a live test where a 2-billion-parameter model tried to pass as a 9-billion one, the honest re-run reproduced the fingerprint exactly and the impostor was rejected at the maximum possible distance.

Forging it is the hard part. Matching the output text of a big model is one thing, and a cheaper model fine-tuned to mimic it might get close. Matching the internal activations is a different problem: to forge those you'd essentially have to run the real model, at which point you saved nothing and had no reason to cheat. What's being verified is the work itself, so faking the proof costs as much as doing the job honestly.

Substituting a weaker model, serving a stale cached answer, running the model at lower precision, or only running part of it all change the internal fingerprint and get caught.

This holds beyond text. The same idea extends to image, audio, and video through a different kind of fingerprint, a step-by-step record of how the output was generated, and it's already been tested on real image, audio, and video engines. The guarantee carries across every modality.
