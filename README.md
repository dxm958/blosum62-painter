<img src="icons/icon-192.png" width="76" alt="">

# BLOSUM Alignment Painter

Align amino acid sequences and shade every column by identity or BLOSUM-62 substitution
similarity, then export a publication-ready SVG or PNG.

**→ [Open the app](https://dxm958.github.io/blosum62-painter/)**

No install, no account, no server: one static HTML file that does all the work in your browser.

**Using it for a figure? Please cite it — see [How to cite](#how-to-cite).**

## The colour rule

| Column | Colour | |
|---|---|---|
| All residues identical | red | `#DC0806` |
| Non-identical, every pair scoring BLOSUM-62 ≥ threshold | orange | `#FE6B00` |
| Anything below threshold, and any column containing a gap | unmarked | |

Stryer's *Biochemistry* (5th ed., §7.2) defines a conservative substitution as one scoring
**> 0**. The more inclusive **≥ 0** is sometimes used instead.

## Getting started

The app opens empty. Paste FASTA into the left-hand panel, or press **Load example** for the
DOA/CLK2 alignment.

## What it does

- **Pairwise alignment** — Needleman–Wunsch, global, affine gaps (Gotoh), BLOSUM-62.
  Presets for Stryer (12/2), EMBOSS (10/0.5) and BLAST (11/1) gap penalties.
- **Pre-aligned input** — paste a Clustal Omega or MUSCLE result and it is coloured as given.
- **Three or more sequences** — a column is shaded only if *every* pair in it qualifies,
  which reduces exactly to the pairwise rule at n = 2.
- **Domain annotations** — `start-end Label` per line, numbered along the first sequence.
- **Export** — SVG (vector, opens in Illustrator/Inkscape) and PNG at 3×, plus the aligned
  FASTA. The figure sheet stays white in dark mode, so what you see is what you print.

## Install it as a desktop app

Open the site in Chrome or Edge and use **Install** in the address bar (Chrome: ⋮ →
Cast, Save and Share → Install page as app). It gets its own window and Dock icon, and works
offline afterwards. In Safari, use **File → Add to Dock**.

You can also download and open `index.html`.

## How to cite

If you use this tool in published work, please cite it:

> McQuarrie DWJ (2026). *BLOSUM Alignment Painter* (v1.5.0).
> https://github.com/dxm958/blosum62-painter

GitHub's **Cite this repository** button renders that as BibTeX or APA from `CITATION.cff`.

## References

The colour scheme implemented here is used in:

> McQuarrie DWJ, Bian W, Soller M (2024). *DOA/CLK2 phosphorylates Fl(2)d/WTAP to enhance
> m<sup>6</sup>A mRNA methyltransferase complex activity.* bioRxiv 2024.11.25.625202.
> <https://doi.org/10.1101/2024.11.25.625202>

Substitution scores are BLOSUM-62:

> Henikoff S, Henikoff JG (1992). *Amino acid substitution matrices from protein blocks.*
> PNAS 89:10915–10919. <https://doi.org/10.1073/pnas.89.22.10915>

The alignment algorithm is Needleman–Wunsch with Gotoh's affine gap costs. Typeface is
IBM Plex (SIL Open Font License).

## The mark

A blossom, for BLOSUM. Its six petals spell the matrix name in amino acid single-letter
codes — **B** (Asx), **L** (Leu), **O** (pyrrolysine), **S** (Ser), **U** (selenocysteine),
**M** (Met) — in the red and apricot of the figures it produces.

## Licence

Code is MIT (see `LICENSE`) — an OSI-approved licence, which software journals such as JOSS
require. Documentation and figures in this repository are CC BY 4.0.
