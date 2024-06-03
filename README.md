# S82X-AGN-Morphology

This repository contains the full catalog of 1,116 Stripe 82X AGNs, along with description of all the labels, for the paper "Morphological Parameters of $z<1$ AGN Host Galaxies in Stripe 82X: Evidence Suggesting a Significant Dependency of AGN-Galaxy Co-evolution on X-ray Luminosity".

## Access to the file
File `S82X_HSC3_z_0_1_GaMPEN_1116_AGN.fits` contains the full catalog. We recommend using an appropriate software , such as [TOPCAT](https://www.star.bris.ac.uk/mbt/topcat/), to access its contents.

## Column Description
Below we provide a comprehensive description for each column contained in the catalog.

### Columns inferented from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)
Please directly refer to `Table 13` in [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d) for column descriptions (from `REC_NO` to `REDSHIFT_FINAL`). There are only a few exceptions that correspond to new columns we added:
- `REC_NO` (training set for `PSFGAN`)
- `fits_eval` (validation set for `PSFGAN`)

