# Why it exists

Two problems show up the moment you run AI on hardware you don't control, and Ogong is built to solve both.

## Problem 1: You can't tell which model actually ran

A provider advertises a big model, say one with 70 billion parameters, then quietly serves an 8-billion one that costs roughly ten times less to run and pockets the difference. The smaller model still produces fluent, plausible text, so you'd never catch it from the output alone.

Re-running the request and comparing doesn't work either. AI inference isn't reproducible bit-for-bit across different hardware. On an Apple M1 Max running a 26-billion-parameter model, simply batching a request alongside other traffic was enough to flip a word in the output, with nothing wrong on either side. So "re-run it and check the bytes" ends up rejecting honest providers, and catching the cheat takes something smarter.

## Problem 2: Whoever runs the machine can read your prompt

When your request lands on someone else's computer, the person who owns that computer has root access to it. On most "decentralized" services your prompt passes through a central server, or onto a stranger's GPU, in plain text. You're trusting them not to read it or log it, and usually there's no technical reason they can't.

For anything sensitive, like your code or your business or a private conversation, "trust us not to look" isn't privacy. It's the same deal a big AI company offers, minus the legal accountability.

Ogong's answer is to solve both with mechanisms instead of promises: make the hardware unable to read the prompt, and make the network able to prove which model ran. Then trusting the operator stops being necessary.
