# Hello, World on Quantum Physics 🌌

<p align="center">
  <a href="README.md">English</a> / <a href="README.ru.md">Русский</a>
</p>

> **Mathematical and physical calculation of running "Hello, World" in a fictional OOP language `psy`**

Оbject-oriented program in the `*.Ψ` language (see [Developer Guide](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/blob/main/en/docs/DEVELOPER-GUIDE.md)).
One class — one physical entity: wave function, collapse upon printing a string,
observer, tunneling in a memory cell, cosmic rays, the Universe.

## Main result (TL;DR)

Model: the program image is **L bytes** of machine code (by default L = 128 bytes,
the minimal x86-64 ELF that prints `Hello, World`), N = 8L bits.
These N bits must spontaneously end up in the required configuration in the memory region
that the OS is ready to execute.

| Model | Mechanism | L = 22 B (only the text `print("Hello, World")`, an interpreter is needed) | **L = 128 B** | L = 142 B |
|---|---|---|---|---|
| **A. Ideal limit** | Ergodic search at the Margolus–Levitin limit, 1 kg computer | ≈ 180 seconds | **≈ 10^250 years** | ≈ 10^284 years |
| **B. Quantum tunneling** | Electron tunneling through a 5 nm SiO₂ barrier | ≈ 10^1904 years | **≈ 10^11158 years** | ≈ 10^12380 years |
| **C. Cosmic rays** | Real soft error rate of DRAM | ≈ 10^1465 years | **≈ 10^8567 years** | ≈ 10^9505 years |

For comparison, the age of the Universe ≈ 1.38·10^10 years = 10^10.14 years.

**Probability of success during the lifetime of the Universe (L = 128 B):**
A — ≈ 10^−240, B — ≈ 10^−11148, C — ≈ 10^−8557.

One bit of "pure" probability: P = 2^−1024 ≈ 5.6·10^−309.

In short: it may not be the fastest or most efficient program, but it works.

## Structure

```
.
├── en/docs/
│   ├── DEVELOPER-GUIDE.md   # .Ψ language, class architecture, diagram
│   ├── 01-THEORY.md         # physical model and assumptions
│   ├── 02-DERIVATIONS.md    # all formulas with derivations
│   ├── 03-RESULTS.md        # full tables of numbers and sensitivity
│   ├── 04-HOWTO-WAIT.md     # instructions: what conditions to create and how long to wait
│   └── 05-FAQ.md            # including "is an observer needed?"
└── src/
    ├── FundamentalConstants.Ψ
    ├── ProgramImage.Ψ
    ├── MemoryCell.Ψ
    ├── Hamiltonian.Ψ
    ├── WaveFunction.Ψ
    ├── CosmicRaySource.Ψ
    ├── Observer.Ψ
    ├── CollapseOperator.Ψ
    ├── WaitingTimeEstimator.Ψ
    ├── UniverseTimeline.Ψ
    └── HelloWorldUniverse.Ψ  # entry point
```

## Quick start for third-party developers

1. Read [Theory](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/blob/main/en/docs/01-THEORY.md) to understand the assumptions.
2. Open [`src/HelloWorldUniverse.Ψ`](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/blob/main/en/src/HelloWorldUniverse.Ψ) — the entry point.
3. Follow the [waiting instructions](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/blob/main/en/docs/04-HOWTO-WAIT.md).
4. Be patient (see the table above).

## Honesty above all

All numbers are calculated with real constants (CODATA 2018): ħ, c, mₑ, eV.
The orders of magnitude are verifiable by hand using the [derivations](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/blob/main/en/docs/02-DERIVATIONS.md).
The model is, of course, simplified, and the assumptions are listed explicitly.

## Contribution and feedback

Found a bug or want to suggest an improvement? Create an [issue](https://github.com/chetsCMD/Hello-World-On-Quantum-Physics/issues). Before submitting, check whether a similar discussion already exists.
Please do not open issues complaining that the program does not work if you have not waited at least 10^8567 years.

## License

MIT.
