# 01 · Theory

## 1. Problem statement

Event **E**: *without human involvement*, an executable image of a program that prints the
string `Hello, World` appears in computer memory, and the processor executes it.

Formalization. The program image is a string of N bits, `|H⟩ = |h₁h₂…h_N⟩`.
The memory state is a vector in a Hilbert space of dimension 2^N:

```
|Ψ⟩ = Σ_x c_x |x⟩,   Σ |c_x|² = 1
```

The probability we need follows from the Born rule:

```
P(E) = |⟨H|Ψ⟩|²
```

If we have no information about the state (maximally mixed state, principle of indifference),
then |c_x|² = 2^−N for every x, and

```
P = 2^−N = 2^−8L
```

This is the "pure" probability of one configuration.

## 2. Model assumptions

| # | Assumption | Default |
|---|---|---|
| D1 | The program image is a minimal x86-64 ELF that prints the string | L = 128 B, N = 1024 bits |
| D2 | The memory region is fixed: the OS simply executes the region (number of positions K = 1) | K = 1 |
| D3 | All 2^N initial configurations of the region are equally likely | uniform |
| D4 | A bit is a double-well system; a transition between wells is tunneling or a thermal/radiation upset | models A–C |
| D5 | The output counts as having happened after the pixel state decoheres | class `Observer` |

If K > 1 (the program may appear in any of K places), the time shrinks by exactly a factor of K,
i.e. a correction of log₁₀K ≈ 11 for 16 GiB. Against 10^250 this is noise, but the class
`WaitingTimeEstimator` accounts for it.

## 3. Three waiting-time models

**Model A — ergodic limit.** The system performs the maximum possible number of distinguishable
quantum transitions per second. For energy E this is the Margolus–Levitin theorem:

```
Γ_max = 2E / (π ħ)
```

For a computer of mass 1 kg (E = mc²): Γ_max ≈ 5.4·10^50 transitions/s (Lloyd's ultimate laptop).
Expected time: T_A = 2^N / Γ_max.

**Model B — tunneling.** A bit is stored as charge behind a barrier. The WKB tunneling
probability is `T = exp(−2κd)`, `κ = √(2mV)/ħ`. For a match, n = N/2 wrong bits must all
flip within a single time window Δt.

**Model C — cosmic rays.** Same as B, but the bit-flip rate comes from real DRAM soft-error
statistics (~1000 FIT/Mbit ⇒ 10^−12 upsets per bit per hour), and the window is the DRAM
refresh period (64 ms).

## 4. Observer and collapse

Before output, the pixel state is a superposition of "pixel lit / not lit" for each character
position. The Born rule gives the outcome probabilities, and the projection operator
`P̂ = |Hello⟩⟨Hello|` describes the measurement "the screen shows Hello, World".
Decoherence makes the pixel basis *pointer states*: the screen quickly (~10^−20 s) "forgets"
superpositions. An honest caveat about whether an observer is needed is in the [FAQ](05-FAQ.md).

## 5. What is not accounted for

- Real bits are correlated: not all 2^N configurations are reachable by soft errors from a given state.
- Interaction of the image with the loader (permissions, file format, MMU) is ignored.
- Times > 10^100 years are outside the applicability of cosmology: the proton may decay and stars
  will go out long before. The formulas remain correct "in a vacuum".
