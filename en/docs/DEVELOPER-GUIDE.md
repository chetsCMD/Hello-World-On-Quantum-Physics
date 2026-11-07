# Developer Guide (the `.Ψ` language)

`.Ψ` is a declarative OOP language for describing physical systems. One file = one class.
Method bodies are written as formulas.

## Syntax

```
class Name [extends Base] {
    constant  name : type = value        // fundamental quantities
    field     name : type                // object state
    method    name(args) → type := formula
}
```

- `⟨a|b⟩` is the inner product, `|x⟩` is a state vector, `Ô` is an operator.
- `log₁₀`, `exp`, `√` are standard functions. `:=` is a definition, `=` is equality.

## Class diagram

```
HelloWorldUniverse (entry point)
 ├─ FundamentalConstants     ħ, c, mₑ, eV, k_B, year
 ├─ ProgramImage             L, N, |H⟩, P = 2^-N
 ├─ MemoryCell               WKB tunneling
 ├─ CosmicRaySource          SER, refresh window
 ├─ Hamiltonian              Γ_max (Margolus–Levitin)
 ├─ WaveFunction             |Ψ⟩, Born rule
 ├─ Observer                 decoherence τ_D
 ├─ CollapseOperator         P̂ = |Hello⟩⟨Hello|, collapse on output
 ├─ WaitingTimeEstimator     models A, B, C
 └─ UniverseTimeline         age of the Universe, P_U
```

## Principles

1. One file, one physical responsibility.
2. No magic numbers: constants only from `FundamentalConstants`.
3. Every formula is either derived in [02-DERIVATIONS.md](02-DERIVATIONS.md) or standard.
4. Results are logarithms (log₁₀), because the numbers are larger than a double.
