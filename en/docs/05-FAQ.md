# 05 · FAQ

### Is an observer needed for "Hello, World" to exist?

Short answer: **no, not in the sense usually implied**.
The program executes, bytes are written to a buffer, and pixels light up whether or not a
human is watching. An "observer" in quantum mechanics is any system that interacts with a
quantum system and irreversibly records information (a detector, surrounding photons, air).
The screen itself is already an excellent "observer" thanks to decoherence (τ_D ~ 10⁻²⁰ s).

In this repository, the classes `Observer` and `CollapseOperator` exist as a *model* of how a
superposition of pixel states turns into a classical outcome. A human is not required in this
model, but can be attached as the last link in the chain.
Interpretations of QM argue about what exactly "collapse" is (Copenhagen, many-worlds, Bohm, etc.);
our calculations use only the Born rule and decoherence, so they do not depend on the interpretation.

### Why so many years?

The program image is 1024 bits. The probability of guessing it at random is 2^−1024 ≈ 10^−308.
Exponential numbers behave like that.

### What if we extend the waiting time?

The probability grows linearly with time (while P·t ≪ 1). For the probability to reach even 1%,
the time must be ≈ 0.01·T. That is still hundreds of orders of magnitude in ages of the Universe. I can only wish patience.

### Can it be sped up?

Only by shrinking the program image or by supplying a "hint": for example, putting a ready-made
`Hello, World` into memory and waiting *only* for it to be launched. But that is no longer a
performance piece, just an ordinary program launch.
