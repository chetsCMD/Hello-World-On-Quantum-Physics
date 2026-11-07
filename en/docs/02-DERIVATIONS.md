# 02 · Derivations

Constants (CODATA 2018): ħ = 1.054571817·10⁻³⁴ J·s, c = 299 792 458 m/s,
mₑ = 9.1093837015·10⁻³¹ kg, 1 eV = 1.602176634·10⁻¹⁹ J, 1 year = 3.15576·10⁷ s.

## 1. Pure probability

`P = 2^−N`, so `log₁₀ P = −N·log₁₀2 = −0.30103·N`.

| L (B) | N (bits) | log₁₀ P |
|---|---|---|
| 22 | 176 | −52.98 |
| 128 | 1024 | −308.25 |
| 142 | 1136 | −341.97 |

## 2. Model A: Margolus–Levitin

Rate of orthogonalization of a state with mean energy E: ν ≤ 2E/(πħ).

```
E = m c² = 1 kg · (299792458)² ≈ 8.988·10¹⁶ J
Γ_max = 2E/(πħ) ≈ 5.43·10⁵⁰ s⁻¹      (log₁₀ = 50.734)
```

Expected time (small p): `T_A = 1/(Γ_max · P)`, i.e.

```
log₁₀ T_A[s] = N·log₁₀2 − 50.734
```

For L = 128: `308.25 − 50.73 = 257.52` ⇒ T_A ≈ 10^257.5 s ≈ 10^250.0 years.

## 3. Model B: tunneling (WKB)

Si/SiO₂ barrier for an electron: V = 3.1 eV = 4.967·10⁻¹⁹ J, effective mass m* = 0.5 mₑ,
thickness d = 5 nm.

```
κ = √(2 m* V)/ħ = 6.378·10⁹ m⁻¹
T = exp(−2 κ d) = exp(−63.78) = 1.99·10⁻²⁸     (log₁₀ T = −27.70)
```

Attempt frequency ν = V/h = 7.50·10¹⁴ Hz. Tunneling rate per bit:

```
r = ν · T ≈ 1.49·10⁻¹³ s⁻¹    (log₁₀ r = −12.83;  mean time ≈ 10^5.3 years)
```

Within a window Δt = 1 ns, each of the n = N/2 "wrong" bits must flip independently:

```
P_window = (r Δt)ⁿ,    log₁₀ P_window = n · log₁₀(r Δt) = 512 · (−21.83)
T_B = Δt / P_window
```

For L = 128: log₁₀ T_B[s] = 11165.8 ⇒ ≈ 10^11158 years.

## 4. Model C: soft errors

SER ≈ 10⁻¹² upsets/bit/hour ⇒ r_C = 2.78·10⁻¹⁶ s⁻¹ per bit (log₁₀ = −15.556).
The window is the DRAM refresh period Δt = 64 ms.

```
T_C = Δt / (r_C Δt)ⁿ,    log₁₀ T_C[s] = −n·log₁₀(r_C Δt) + log₁₀Δt
```

For L = 128: ≈ 10^8574.9 s ≈ 10^8567 years.

## 5. Probability within the lifetime of the Universe

Age of the Universe U = 4.35·10¹⁷ s (log₁₀ = 17.64). For T ≫ U:

```
P_U ≈ U / T      ⇒    log₁₀ P_U = 17.64 − log₁₀ T[s]
```

| L | A | B | C |
|---|---|---|---|
| 22 | ≈ 1 (180 s ≪ U) | 10^−1894 | 10^−1455 |
| 128 | 10^−239.9 | 10^−11148 | 10^−8557 |
| 142 | 10^−273.6 | 10^−12370 | 10^−9495 |

Number of steps of a 1 kg ultimate computer over the age of the Universe: `Γ_max · U ≈ 10^68.4`.
We needed 10^308.25. That is ~239.9 orders of magnitude short.

## 6. Pixel decoherence

```
τ_D = τ_R · (λ_th/Δx)²,   λ_th = ħ/√(2 m k_B T)
```

Electron, T = 300 K: λ_th ≈ 1.2 nm. With Δx = 1 µm and τ_R ~ 10⁻¹⁴ s:
`τ_D ≈ 10⁻¹⁴ · (1.2·10⁻³)² ≈ 1.5·10⁻²⁰ s`. An illustrative order-of-magnitude estimate.
