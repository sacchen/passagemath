# passagemath — Claude Notes

## Known hallucinations / past misdiagnoses

### Issue #2254 investigation (2026-03-07)

**Hallucinated package:** `passagemath-sympy` does not exist.
SymPy is a *standard* (non-optional) upstream dependency (`build/pkgs/sympy`, type=`standard`).
It is a *required* dependency of `passagemath-symbolics`, not an optional one.
Any `try: import sympy / except ImportError: pass` blocks are legacy no-ops — sympy is always present.
The diagnosis that `chart_func.py` had a real NameError risk was wrong.

**Inflated pari count:** Claimed "~43 unguarded uses of `pari`" in `number_field.py`.
The grep filter `grep -v "sage:"` does not exclude *indented* doctest lines (`            sage: pari(...)`).
The real count of executable (non-doctest) uses is ~24–25, consistent with the original "27" estimate.

## Dependency notes

- `sympy`: standard pip dependency, always available when `passagemath-symbolics` is installed
- `pari` / `cypari2`: optional, gated by `passagemath-pari`; the `try/except ImportError` pattern in
  `ell_point.py` and `number_field.py` does leave `pari` unbound — that is a real issue
