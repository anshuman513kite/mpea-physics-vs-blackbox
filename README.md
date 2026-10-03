# Do dislocation-physics features predict alloy strength better than a black box?

**Status: in progress**

## Question
Multi-principal-element alloys (MPEAs, incl. high-entropy alloys) are strengthened
largely by solute–dislocation interactions. Classical theory points to a few
physical drivers: atomic size misfit, shear modulus mismatch, and valence electron
concentration (VEC).

This project tests one question:
**Can a small set of physics-based features predict MPEA yield strength as well as,
or better than, a black-box model on raw composition — when tested on alloy
families the model has never seen?**

## Data
Borg et al. (2020), *Expanded dataset of mechanical properties and observed phases
of multi-principal element alloys*, Scientific Data 7, 430.
https://doi.org/10.1038/s41597-020-00768-9
~630 unique alloys (~1,500 records): composition, processing, microstructure,
hardness, yield strength, test temperature.

## Method (planned)
1. Clean data; handle repeated alloys and test temperature
2. Compute physics features (size misfit δ, modulus mismatch, VEC) from composition
3. Baseline: black-box model on composition fractions
4. Physics model: same learner on physics features only
5. **Group cross-validation by alloy family** — avoids leakage from the same alloy
   appearing in train and test
6. Compare errors; one key chart; short answer

## Why this matters
Random train/test splits flatter materials ML models. Family-wise validation
asks the harder, practical question: will the model help with a *new* alloy system?

## Author
Anshuman Choudhury — PhD Computational Materials Science (Université Paris-Saclay / CEA),
atomistic simulation of dislocation dynamics in BCC metals.
