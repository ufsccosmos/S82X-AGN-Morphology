# S82X-AGN-Morphology

This repository contains the full catalog of 1,116 Stripe 82X AGNs, along with description of all the labels, for the paper "Morphological Parameters of $z<1$ AGN Host Galaxies in Stripe 82X: Evidence Suggesting a Significant Dependency of AGN-Galaxy Co-evolution on X-ray Luminosity" (hereafter `the paper`).

## Access to the file
File `S82X_HSC3_z_0_1_GaMPEN_1116_AGN.fits` contains the full catalog. We recommend using an appropriate software, such as [TOPCAT](https://www.star.bris.ac.uk/mbt/topcat/), to access its contents.

## Citation Information
If you use our data in your publication, please reference `the paper` at (Link). (Under Construction --- paper link will be updated after the reviewing process is completed)
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
- `Separation`: Distance between position `CTP_RA, CTP_DEC` (from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d)) and position `ra, dec` (from [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced), described above) (in degree)
- `match_by_mag`: Which band(s) is(are) used in cross-matching. For instance, `g` means that we have used column `G` from [Ananna et al. 2017](https://iopscience.iop.org/article/10.3847/1538-4357/aa937d) and column `g_cmodel_mag` from [pdr3_wide.forced](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.forced) in cross-matching, together with the positional information.
- `file_name`: File name of the image. Only used internally. 

### Columns from running [PSFGAN](https://academic.oup.com/mnras/article/477/2/2513/4951616)
- `contrast_ratio`: After separating the AGN point source and the host galaxy, we calculated the AGN-to-host galaxy flux contrast ratio (in the corresponding band, depending on the redshift --- see `Table 1` in the paper).

### Columns from running [GaMPEN](https://ghosharitra.com/gampen.html)
Here we use $R_e$ (effective radius) as an example. Cases are similar for other morphological parameters. Note that this information is valid for the corresponding band only (depending on the redshift --- see `Table 1` in the paper).
- `preds_R_e_asec_mean`: Mean of `GaMPEN` predicted distribution for parameter $R_e$ (in arcsec --- the same unit is used for other $R_e$ columns)
- `preds_R_e_asec_median`: Median of `GaMPEN` predicted distribution for parameter $R_e$ 
- `preds_R_e_asec_std`: Standard deviation  of `GaMPEN` predicted distribution for parameter $R_e$ 
- `preds_R_e_asec_skew`: Skewness of `GaMPEN` predicted distribution for parameter $R_e$ 
- `preds_R_e_asec_kurtosis`: Kurtosis of `GaMPEN` predicted distribution for parameter $R_e$ 
- `preds_R_e_asec_mode`: Mode of `GaMPEN` predicted distribution for parameter $R_e$ (i.e., the most probable value of $R_e$ in the entire predicted distribution)
- `preds_R_e_asec_sig_ci`: Lower and upper bounds for the 1 $\sigma$ confidence interval for parameter $R_e$
- `preds_R_e_asec_twosig_ci`: Lower and upper bounds for the 2 $\sigma$ confidence interval for parameter $R_e$
- `preds_R_e_asec_threesig_ci`: Lower and upper bounds for the 3 $\sigma$ confidence interval for parameter $R_e$

Note for other morphological parameters, units are different. For instance, total flux is in ADU (analog-to-digital units) while the bulge-to-total ratio (`bt`) is unitless.

### Columns from [pdr3_wide.photoz_demp](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.photoz_demp)
- `stellar_mass_DEmP`: Mode stellar mass derived from P(M*), in the unit of solar mass in log scale [Msun]
- `stellar_mass_err68_min_DEmP`: 16% percentile in the P(M*) [Msun]
- `stellar_mass_err68_max_DEmP`: 84% percentile in the P(M*) [Msun]
- `sfr_DEmP`: Mode star formation rate derived from P(SFR), in the unit of solar mass per year in log scale. [Msun/yr]
- `sfr_err68_min_DEmP`: 16% percentile in the P(SFR) [Msun/yr]
- `sfr_err68_max_DEmP`: 84% percentile in the P(SFR) [Msun/yr]
- `ssfr_DEmP`: Specific star formation rate (sSFR) calculated using `stellar_mass_DEmP` and `sfr_DEmP` [/yr]

### Columns from [pdr3_wide.photoz_mizuki](https://hsc-release.mtk.nao.ac.jp/schema/#pdr3.pdr3_wide.photoz_mizuki)
- `stellar_mass_mizuki`: Median stellar mass [Msun]
- `stellar_mass_err68_min_mizuki`: Lower bound of the 68% confidence interval of stellar_mass [Msun]
- `stellar_mass_err68_max_mizuki`: Upper bound of the 68% confidence interval of stellar_mass [Msun]
- `sfr_mizuki`: Median star formation rate [Msun/yr]
- `sfr_err68_min_mizuki`: Lower bound of the 68% confidence interval of star formation rate [Msun/yr]
- `sfr_err68_max_mizuki`: Upper bound of the 68% confidence interval of star formation rate [Msun/yr]
- `ssfr_mizuki`: Specific star formation rate (sSFR) calculated using `stellar_mass_mizuki` and `sfr_mizuki` [/yr]
- `rest_galex_(fuv|nuv)_mag`: Rest-frame GALEX (FUV|NUV) magnitude [mag]
- `rest_sdss_(u|g|r|i|z)_mag`: Rest-frame SDSS (u|g|r|i|z)-band magnitude [mag]
- `rest_hsc_(g|r|i|z|y)_mag`: Rest-frame HSC (g|r|i|z|y)-band magnitude [mag]
- `rest_wfcam_(y|j|h|k)_mag`: Rest-frame WFCAM (Y|J|H|K)-band magnitude [mag]
  








