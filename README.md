# Sign Flips and Linear Mode Connectivity: Interactive Simulators

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23314245.svg)](https://doi.org/10.5281/zenodo.23314245)

**Mrigesh Lakhanpal** · ORCID [0009-0007-9539-9091](https://orcid.org/0009-0007-9539-9091) · Companion to preprint v2, October 2026

🌐 **Live site:** https://mrigeshlakhanpal.github.io/sign-flips-lmc-simulators/
📄 **Preprint, code and results:** [`sign-flips-lmc`](https://github.com/MrigeshLakhanpal/sign-flips-lmc) · DOI: [10.5281/zenodo.23314245](https://doi.org/10.5281/zenodo.23314245)

## Summary

Interactive explainers for *A Missing Sign Symmetry Accounts for the Linear-Mode-Connectivity Barrier in Minimal-Width Sigmoid Networks*. For irreducible one-hidden-layer sigmoid networks, the exact symmetries are permutations and sign flips (2^h·h! elements), and a permutation-only matcher cannot undo a flip. Each page opens with a plain-language question and a predict-first game, then an interactive, then the technical statement.

This repository holds only the explanatory layer; it does not re-run the experiments. Sign-aware alignment itself is prior work (Pittorino et al. 2022; Boufalis et al. 2025). ReLU networks have no sign flip and are not addressed.

| # | Question | Type | Evidence |
|---|----------|------|----------|
| 5 | Why is merging models so hard? | Rotatable weight-space view (Three.js) with spare-unit detour and output-change telemetry | Exact geometry of Eq. 3 and Lemma 1 for one toy unit |
| 6 | What does the loss landscape really look like? | Rotatable schematic loss surface, spare dimension on/off | Schematic, illustrative only |
| 7 | Do two networks trained from different seeds learn the same thing? | Live in-browser training, flip detection, barrier before/after alignment, capacity scan | Live mini-replication (simplified polygons), not the preprint's data |
| 8 | Can your measurement hide what is really happening? | Scoreboard, interval plot, saturation schematic | Preprint Sec. 5.1 and 5.4; schematic curves |
| 1 | If two networks compute the same function, why can't you average them? | Prediction game, flip-blend simulator, heat map, rotatable 3D surface | Toy model of Eq. 3 and Lemma 1 |
| 2 | If two solutions are secretly the same, why is there a hill between them? | Rotatable loss landscape | Toy model, illustrative only |
| 3 | When does "a missing symmetry explains it" stop being enough? | Task-by-threshold heat map, predict then reveal | Preprint Tables 5 and 6 (Study 2) |
| 4 | Does making the network wider make the problem go away? | Barrier-versus-width graph with 95% intervals | Preprint Table 8 (Study 1, coffee task) |

`docs/explainer.html` is an all-in-one walkthrough of the paper.

## How evidence is labelled

- **PAPER**: numbers transcribed from the preprint's tables, with no re-computation or smoothing.
- **TOY MODEL**: a simplified simulation for intuition, not an experimental result (simulators 1 and 2).
- **EXPLORATORY**: analyses the preprint marks as decided after seeing results.

The toy models were checked numerically: the sign-flip identity holds to about 1e-15, the midpoint change is bounded by |s|/2 (5.568 against 5.57 for s = −11.14), and the spare-unit path keeps the function constant. The ring valley in simulator 2 is a picture, not the measured landscape: in the preprint a flat path between symmetry copies exists with one spare unit, which does not by itself show a zero straight-line barrier.

## Run locally

Pages 1–4 are self-contained HTML files; pages 5–6 load one pinned script (three.js r128) from cdnjs, so they need an internet connection. Open `docs/index.html`, or serve the folder:

```
python -m http.server 8000 --directory docs
```

## Repository layout

| Path | Contents |
|------|----------|
| `docs/index.html` | Landing page (GitHub Pages root) |
| `docs/explainer.html` | All-in-one paper walkthrough |
| `docs/sim1-why-averaging-fails.html` | Simulator 1 |
| `docs/sim2-loss-landscape.html` | Simulator 2 |
| `docs/sim3-where-claim-fails.html` | Simulator 3 |
| `docs/sim4-barrier-vs-width.html` | Simulator 4 |
| `docs/m1-merging.html` | Simulator 5 (loads three.js r128 from cdnjs) |
| `docs/l1-landscape.html` | Simulator 6 (loads three.js r128 from cdnjs) |
| `docs/lab-live-training.html` | Simulator 7 (live training, self-contained) |
| `docs/f1-failed-prediction.html` | Simulator 8 |
| `CITATION.cff` | Citation metadata |

## Data and credit

Values in simulators 3 and 4 are transcribed from the preprint (Study 1 uses the coffee-roasting task from the *Machine Learning Specialization*, Andrew Ng, DeepLearning.AI and Stanford Online). No course files and no model files are included here; see the research repository for code and result files.

## Use of AI assistance

These simulators were built with Claude (Anthropic) as an AI design and coding assistant, under my direction. The preprint's *Authorship and use of AI assistance* section describes the wider use. Transcribed values were audited against the preprint's tables.

## Citation

```
@misc{lakhanpal2026signflips,
  author = {Mrigesh Lakhanpal},
  title  = {A Missing Sign Symmetry Accounts for the Linear-Mode-Connectivity Barrier in Minimal-Width Sigmoid Networks},
  year   = {2026},
  note   = {Preprint, v2},
  doi    = {10.5281/zenodo.23314245},
  url    = {https://github.com/MrigeshLakhanpal/sign-flips-lmc}
}
```

## License

Code (HTML, CSS, JavaScript): MIT (see `LICENSE`). Explanatory text, figures and numbers transcribed from the preprint: CC BY 4.0 (see `LICENSE-CC-BY-4.0.md`), as in the research repository.
