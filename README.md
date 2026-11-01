# CASIO fx-50FH II · Web Emulation

A single-file web calculator that recreates the **CASIO fx-50FH II**, the HKEAA-approved
programmable scientific calculator used by HKDSE candidates in Hong Kong.

- **Live page:** <https://tyhcch1234.github.io/casio-fx-50fhii/>
- **Source:** [`index.html`](index.html) — one file, no build step, no dependencies.

## Matched to the real device

The layout is taken from the official product page for the fx-50FHII
(<https://www.casio.com/hk/scientific-calculators/product.FX-50FHII/>), key row by key row:

- Charcoal outer shell, warm silver face plate, `CASIO` / `fx-50FH Ⅱ` wordmark.
- Solar strip with four cells, the orange `H.K.E.A.A. APPROVED` bar and `SUPER-FX PLUS`.
- Pale blue-grey two-line dot-matrix LCD with a recessed metal bezel.
- Ovoid `SHIFT` / `ALPHA` / `MODE SETUP` / `ON` keys around the round `REPLAY` wheel.
- Orange `Prog` / `FMLA`, dark-red `DEL` / `AC`, and six-column function rows above a
  five-column numeric block — the same key order as the physical unit.
- Every printed legend above a key is reproduced: gold for SHIFT, red for ALPHA
  variables, teal for ALPHA functions.

## Key operation works the same way

| Press | What happens |
|---|---|
| `SHIFT` then a key | runs the gold legend above that key. A key with no gold legend does **nothing** (it does not fall through to the main function) — same as the device. |
| `ALPHA` then a key | inserts the red variable (`A`–`F`, `X`, `Y`, `M`, `i`) or the teal function (`LOGIC`, `DEC`, `HEX`, `BIN`, `OCT`). |
| `MODE` | opens the on-screen mode menu — `1:COMP 2:CMPLX 3:BASE 4:SD 5:REG 6:PRGM`. Choose with the number keys, arrows select, `EXE` confirms, `AC`/`DEL` cancels. |
| `SHIFT` `MODE` | opens SETUP: angle unit → display format → digit count, one menu page at a time. |
| `SHIFT` `1` / `SHIFT` `2` | S-SUM / S-VAR statistics menus in SD and REG modes. |
| `RCL` + letter | recalls a variable and shows its value. `SHIFT` `RCL` (STO) + letter stores the displayed value. |
| `M+` | adds to independent memory, or enters a data point while in SD / REG. |
| `a b/c` / `SHIFT` `a b/c` | toggles the result between mixed fraction, improper fraction and decimal. |
| `DEL` / `AC` / `ON` | delete character, clear everything, power on. |
| `REPLAY` ◀ ▶ / ▲ ▼ | move the caret, or walk the calculation history. |

`S` and `A` appear in the status row while a modifier is armed, exactly like the device's
own indicators.

## Calculating

| Area | Supported |
|---|---|
| Arithmetic | `+ − × ÷`, `^`, parentheses, unary minus, implicit multiplication (`2π`, `3(4+1)`) |
| Trigonometry | `sin cos tan`, inverses, hyperbolics and inverses, DEG / RAD / GRA |
| Logs & powers | `log`, `ln`, `10ˣ`, `eˣ`, `√`, `∛`, `x²`, `x³`, `x⁻¹`, `xʸ` |
| Combinatorics | `!`, `nPr`, `nCr` |
| Entry | `EXP` (`2×10^3`), `π`, `e`, `%`, degrees-minutes-seconds (`1°30°0`), `Ran#`, `Rnd`, `Pol(`, `Rec(` |
| Formats | `Norm`, `Fix 0–9`, `Sci 0–9`, `Eng`, `DEC / HEX / BIN / OCT` view |
| Memory | `M`, `M+`, `M−`, `STO`, `RCL`, variables `A`–`F`, `X`, `Y`, `Ans` |
| **COMP** | the full engine |
| **CMPLX** | complex arithmetic — `i` on `ALPHA` `ENG`, results as `a+bi` |
| **SD** | 1-variable statistics: `n`, `x̄`, `σn`, `σn-1`, `Σx`, `Σx²` |
| **REG** | linear regression: `a`, `b`, `r` |
| **BASE / PRGM** | shown in the MODE menu; choosing them reports that they are not included |

## Deliberate limitations

These fx-50FH II features are **not** emulated, because they need device-level state that a
web page cannot honestly reproduce:

- **PRGM mode** (4 program areas, 680 bytes of BASIC-like programs).
- **BASE-n mode** — only the DEC/HEX/BIN/OCT *view* of a result works, not native base
  arithmetic.
- **Built-in formulas** (23) and **scientific constants** (40).
- **Σ / ∫** summation and integration, and the **SD / REG** editor's full data table.

Every other key on the keypad does something real; the ones above report themselves
instead of failing silently.

## Run it locally

```bash
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

## Disclaimer

This is an independent study aid. It is **not** a CASIO product, it is not affiliated with
CASIO, and it is **not** an HKEAA-approved device — do not expect to bring a laptop running
this page into an examination hall.

## License

MIT.
