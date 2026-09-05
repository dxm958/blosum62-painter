# BLOSUM Alignment Painter

Align amino acid sequences and shade every column by identity or BLOSUM-62 substitution
similarity, then export a publication-ready SVG or PNG.

**→ [Open the app](https://dxm958.github.io/blosum62-painter/)**

No install, no account, no server: one static HTML file that does all the work in your browser.
Your sequences never leave your machine.

## The colour rule

| Column | Colour | |
|---|---|---|
| All residues identical | red | `#DC0806` |
| Non-identical, every pair scoring BLOSUM-62 ≥ threshold | orange | `#FE6B00` |
| Anything below threshold, and any column containing a gap | unmarked | |

The default threshold is **≥ 0**, which reproduces the scheme used in Supplementary Fig. 1 of
McQuarrie, Bian & Soller, *DOA/CLK2 phosphorylates Fl(2)d/WTAP to enhance m6A mRNA
methyltransferase complex activity*.

Note that Stryer's *Biochemistry* (5th ed., §7.2) defines a conservative substitution more
strictly, as a score **> 0**. One click switches between the two. The difference is not
cosmetic — on the DOA/CLK2 alignment it is 99 similar columns versus 60, because BLOSUM-62
scores exactly 0 for pairs such as A/G, A/V, D/S, E/H, E/N, E/R, E/S, F/I, G/S, H/Q, H/R,
K/N, K/S, Q/S and T/V.

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

You can also just download `index.html` and double-click it — it is fully self-contained.

## Citing

Use the **Cite this repository** button, or mint a DOI: link the repo at
[zenodo.org/account/settings/github](https://zenodo.org/account/settings/github), then publish
a GitHub release. Zenodo archives that release and issues a permanent DOI, free.

## Credits

Substitution scores are BLOSUM-62 (Henikoff & Henikoff, *PNAS* 89:10915–10919, 1992).
Typeface is IBM Plex (SIL Open Font License).

MIT licensed.
