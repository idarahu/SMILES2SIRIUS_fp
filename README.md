# SMILES2SIRIUS_fp

## Overview
SMILES2SIRIUS_fp is a Nextflow pipeline designed for calculating SIRIUS+CSI:FingerID fingerprints for chemicals based on their SMILES representations. 

## Usage
### Configuration 
Edit the `main.nf` script to customize parameters such as:
- `params.data`: Path to the input (.tsv) file containing SMILES data.
- `params.batch_size`: Size of SMILES blocks processed together.
- `params.mode`: Select fingerprint mode (`pos`, `neg`, `overlapping`).

### Output
The pipeline generates SIRIUS+CSI:FingerID fingerprint files (.tsv) based on the selected mode:
- positive ionization mode fingerprint: files named `pos_*.tsv`;
- negative ionization mode fingerprint: files named `neg_*.tsv`;
- overlapping fingerprint: files named `overlapping_*.tsv`, containing features present in both positive and negative mode fingerprints.
Additionally, it outputs a 'raw' fingerprint files (files named `raw_*.tsv`)  that includes all computable fingerprint features by SIRIUS+CSI:FingerID, regardless of the ionization mode.
Results are stored in the `results` directory.
