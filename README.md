# FASTA Duplicate Sequence Remover

This repository contains an R script to remove duplicate sequences from a FASTA file and save the unique sequences to a new FASTA file. The script reads a FASTA file, identifies duplicate sequences, and retains only one occurrence of each sequence.

## Features

- Reads sequences from a FASTA file.
- Identifies and removes duplicate sequences.
- Writes unique sequences to a new FASTA file.

## Requirements

- R (version 4.0 or later)
- RStudio (optional but recommended)

### R Packages

The following R package is required to run the script:

- seqinr

You can install this package using the following command:

```r
install.packages("seqinr")
