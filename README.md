# Real zeros and consecutive interlacing of excedance polynomials with a minimum cycle length

Qiyuan Ma, School of Artificial Intelligence, Shanghai Jiao Tong University, Shanghai, China.
ORCID: https://orcid.org/0009-0000-9532-0821
Email: mqyqwerty@sjtu.edu.cn

Verification draft, 27 November 2026. DOI: https://doi.org/10.5281/zenodo.24583559. The manuscript and supplement present a computer-assisted candidate proof covering all integers n ≥ k ≥ 3. No independent mathematical review or formal verification is claimed. The project is not a study of descents.

This preprint and the companion materials are released under the Creative Commons Attribution 4.0 International License (CC-BY-4.0). See `LICENSE.md` and https://creativecommons.org/licenses/by/4.0/.

In this repository, the preprint PDF is [`Long-Cycle-Excedance-Preprint.pdf`](Long-Cycle-Excedance-Preprint.pdf) (the same file as `manuscript.pdf` in the archive). [`Long-Cycle-Excedance-Reproduction.zip`](Long-Cycle-Excedance-Reproduction.zip) unpacks to `Long-Cycle-Excedance-Preprint-v1/`. The sections below describe that directory. `manuscript.tex` and `LICENSE.md` are also at the repository root.

## Read
- `manuscript.pdf`: English AMS-style preprint.
- `manuscript.tex`: source (AMS-LaTeX and standard TeX Live packages, no external assets or BibTeX). Run `pdflatex -halt-on-error manuscript.tex` twice.
- `PROOF-MAP.md`: read in parallel with Sections 5 and 6 of the paper. The notes and certificates are part of the proof.
- `LICENSE.md`: CC-BY-4.0 statement for the preprint and companion materials.

## Verify
Requires Node.js 24 or a compatible recent release with BigInt, and Python 3.12 or a compatible recent release. No third-party packages are needed for the entry points below. Do not run Python with `-O` or set `PYTHONOPTIMIZE`; that disables certificate assertions. From this directory:

```text
python -B verify.py quick
python -B verify.py bands
python -B verify.py fixed
```

- **quick** runs the eight certificate programs for the closing bands k=14,15.
- **bands** runs the stored JavaScript scripts for analytic bounds, as well as selected earlier Python analytic certificates. A successful execution is not a substitute for checking the proof of each bound in the corresponding note.
- **fixed** replays exact finite prefixes for k=3–13. The largest prefixes can take tens of minutes or longer depending on hardware. See the proof map for individual commands. Earlier k=12 and k=13 output is preserved under `Supplement/earlier/analysis/`.
- The verifier stops on a nonzero exit. Numeric prints in the JavaScript programs may be rounded for display; the decisive inequality comparisons are BigInt-based. The archive does not claim a formal proof kernel or any aggregate model-usage figure.

The paper was developed with substantive assistance from OpenAI ChatGPT. This draft is for checking and preparation, not an assertion of external endorsement or publication priority.
