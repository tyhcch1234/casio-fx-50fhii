# CASIO fx-50FH II · Web Emulation

A single-file web calculator that recreates the **CASIO fx-50FH II** — the HKEAA-approved
programmable scientific calculator used by HKDSE candidates in Hong Kong.

- **Live page:** <https://tyhcch1234.github.io/casio-fx-50fhii/>
- **Source:** [`index.html`](index.html) — one file, no build step, no dependencies.

![keypad](https://img.shields.io/badge/keypad-fx--50FH%20II-df7434) ![single file](https://img.shields.io/badge/single%20file-HTML%2BCSS%2BJS-2b2e34)

## What it does

The point of the project is fidelity: the case, the solar strip, the two-line
dot-matrix LCD, the SHIFT/ALPHA silk-screen legends, and the exact key rows of the
real device — driven by a real calculation engine rather than a scripted demo.

### Interface

- Silver shell with CASIO / `fx-50FH Ⅱ` branding, H.K.E.A.A. APPROVED strip, solar panel.
- Green-grey LCD with a dot-matrix texture, a status row
  (`SHIFT`, `ALPHA`, `M`, `hyp`, angle unit, number format), an expression line and a
  right-aligned result line.
- Yellow SHIFT and red ALPHA legends printed above every key; the keypad highlights the
  keys that actually have a SHIFT / ALPHA function while the modifier is armed.
- Six-column function block over a five-column numeric block, matching the original layout.

### Calculation

| Area | Supported |
|---|---|
| Arithmetic | `+ − × ÷`, `^`, parentheses, unary minus, implicit multiplication (`2π`, `3(4+1)`) |
| Trigonometry | `sin cos tan`, `sin⁻¹ cos⁻¹ tan⁻¹`, `sinh cosh tanh` and inverses, DEG / RAD / GRA |
| Logs & powers | `log`, `ln`, `10ˣ`, `eˣ`, `√`, `∛`, `x²`, `x³`, `x⁻¹`, `ˣ√` |
| Combinatorics | `!`, `nPr`, `nCr` |
| Number entry | `EXP` (`2E3`), `π`, `e`, `%`, degrees-minutes-seconds (`1°30°0`) |
| Display formats | `Norm`, `Fix 0–9`, `Sci 0–9`, `Eng` |
| Fractions | `a b/c` shows a mixed number, `d/c` shows an improper fraction, `S⇔D` back to decimal |
| Memory | independent `M`, `M+`, `M−`, `STO`, `RCL`, `Ans` |
| Extras | `Ran#`, `Rnd`, `RanInt`, `Abs`, `Pol(`, `Rec(` |
| Editing | caret movement, `DEL`, `INS`, multi-replay history with ↑ / ↓ |

### Keyboard

`0–9` `.` `+ - * /` `^` `( )` `,` `%` `!` `Enter`=EXE `Backspace`=DEL `Esc`=AC
`←` `→` move the caret, `↑` `↓` replay history.

## Run it locally

```bash
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

No server, no install — the file is fully self-contained.

## Deliberate limitations

These fx-50FH II features are **not** emulated, because they need device-level state
that a web page cannot honestly reproduce:

- **PRGM mode** (4 program areas, 680 bytes of BASIC-like programs) — the `Prog` key
  reports that the mode is not included.
- **Built-in formulas** (23) and **scientific constants** (40) — the `FMLA` key reports
  the same.
- **Σ / ∫** summation and integration, and the **SD / REG** statistics editor.

Everything else on the keypad works. If you need one of the missing modes, open an issue.

## Disclaimer

This is an independent study aid. It is **not** a CASIO product, it is not affiliated
with CASIO, and it is **not** an HKEAA-approved device — do not expect to bring a laptop
running this page into an examination hall.

## License

MIT.
