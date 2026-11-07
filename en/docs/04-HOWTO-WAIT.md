# 04 · Instructions: how to wait for "Hello, World"

## Step 0. Choose an image

The shorter the image, the better: each byte costs ×256 in waiting time.
Minimize the ELF header (overlap ELF/program header fields), use `write` + `exit`.

## Step 1. Create the conditions

| Condition | Why | How |
|---|---|---|
| Fixed execution region | K = 1, do not dilute the probability | Run `execve` on a file the OS considers executable |
| Maximum transition rate Γ | T ∝ 1/Γ | Model A: more energy E ⇒ Γ = 2E/(πħ). In practice: more cores, higher clocks |
| Thin barrier | exponential growth of tunneling | As small a d as possible (without melting the crystal) |
| High cosmic-ray flux | higher SER | Work at altitude (Elbrus, aircraft ~ ×100–300) |
| No ECC | ECC corrects single upsets | You need memory without error correction |
| Time | Always | See step 3 |

## Step 2. Run

```
run HelloWorldUniverse.Ψ  →  method wait()
```

## Step 3. How long to wait

For L = 128 B (see the [table](03-RESULTS.md)):

- **In the ideal limit (A):** ≈ 10^250 years.
- **Via tunneling (B):** ≈ 10^11158 years.
- **Via cosmic rays (C):** ≈ 10^8567 years.

The age of the Universe is ≈ 1.4·10^10 years. The wait therefore exceeds the age of the Universe
by more than a factor of 10^239. We recommend bringing a book.

## Step 4. The observer

Once the string has appeared, make sure someone has looked at it. See the [FAQ](05-FAQ.md).
