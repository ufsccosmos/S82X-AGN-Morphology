# S82X-AGN-Morphology

This repository contains the full catalog of 1,116 Stripe 82X AGNs, along with description of all the labels, for the paper "Morphological Parameters of $z<1$ AGN Host Galaxies in Stripe 82X: Evidence Suggesting a Significant Dependency of AGN-Galaxy Co-evolution on X-ray Luminosity" (hereafter `the paper`).

## Access to the file
File `S82X_HSC3_z_0_1_GaMPEN_1116_AGN.fits` contains the full catalog. We recommend using an appropriate software , such as [TOPCAT](https://www.star.bris.ac.uk/mbt/topcat/), to access its contents.

## Column Description
Below we provide a comprehensive description for each column contained in the catalog.

### Columns from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)
Please directly refer to `Table 13` in [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d) for column descriptions (from `REC_NO` to `REDSHIFT_FINAL`). There are only a few exceptions that correspond to new columns we added:
- `REDSHIFT_FINAL`: Equals to column `REDSHIFT` (spectrospic redshift from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)) if available. Otherwise, it equals to column `PHOTOZ` (photometric redshift from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)). Unless otherwise specified, `REDSHIFT_FINAL` is the redshift ($z$) we used throughout the paper.
- `LUMINOSITY_FINAL`: Equals to column `LUMINOSITY_SPEC` (full band X-ray luminosity calculated using `REDSHIFT` in [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)) if available. Otherwise, it equals to column `LUMINOSITY_PHOT` (full band X-ray luminosity calculated using `PHOTOZ` in [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)). Unless otherwise specified, `LUMINOSITY_FINAL` is the X-ray luminosity ($L_x$) we used throughout the paper.

### Columns from HSC DR3 table [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced)
- `object_id`: Unique ID in 64bit integer. Be careful not to have it converted to a 32bit integer or 64bit floating point.
- `ra`: RA (J2000.0) of the object (in degree)
- `dec`: DEC (J2000.0) of the object (in degree)
- `tract`: Tract ID. 
- `patch`: Patch name as an integer.
- `(g|r|i|z|y)_cmodel_mag`: flux from the final cmodel fit (in mag)
- `(g|r|i|z|y)_cmodel_magerr`: flux uncertainty from the final cmodel fit (in mag)
- `(g|r|i|z|y)_extendedness_value`: Set to 1 for extended sources, 0 for point sources. See [this page](https://hsc-release.mtk.nao.ac.jp/doc/index.php/star-galaxy-separation__pdr3/) for details.

### Columns from cross-matching [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d) with [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced)
- `Separation`: Distance between position `CTP_RA`, `CTP_DEC` (from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)) and position `ra`, `dec` (from [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced), described above) (in degree)
- `match_by_mag`: Which band(s) is(are) used in cross-matching. For instance, `g` means that we have used column `G` from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d) and column `g_cmodel_mag` from [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced) in cross-matching, together with the positional information.
- `file_name`: File name of the image. Only used internally. 

### Columns from [PSFGAN](https://academic.oup.com/mnras/article/477/2/2513/4951616)
- `contrast_ratio`: After separating the AGN point source and the host galaxy, we calculated the AGN-to-host galaxy flux contrast ratio (in the corresponding band, depending on the redshift --- see `Table 1` in the paper).
