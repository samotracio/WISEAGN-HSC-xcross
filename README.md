# WISEAGN-HSC-xcross
---
This contains the files, codes and notebooks to select AGN, classifiy, filter, and perform crosscorrelations between WISE AGN and HSC galaxies. Note this repo contains only the small data files. Any input file not present here is available in the shared google drive folder.

### gmm_split.ipynb
This implements a log-normal mixture model to separate between obscured/unobscured. Theres is a threshold to separate objects with uncertain classifitation into a third class. To run this notebook you need C75_hscmatched2arcs_wisematched2arcs.fits, which is Google Drive

### wiseagn_cross_hsc.ipynb
This notebook has two parts: the first one is to select various subsamples of AGN, plus the galaxies, plus the randoms. The second actually calculates the CCFs and generate plots. To run you need the AGN catalog with classifications C75_hpwm_gmmclass.parquet (ouput by gmm_split.ipynb), masked_hpwm_hscx_c_gal.parquet (the HSC galaxies), and hpwm_randoms.parquet (a big pool of 100 mill randoms for HSC galaxies). I have put these files in Google Drive.

### CNT files
These are the ouput cnt files that Gundam produces for each correlation run. You can plot directly from these. Check the names in wiseagn_cross_hsc.ipynb to associate each run to its sample, that is:

* hpwm_unobsc_lrg_0510.cnt : cross-correlation between unobscured and lrg within the HSC+WISE mask, 0.5<z<1.0
* hpwm_obsc_lrg_0510.cnt : cross-correlation between obscured and lrg within the HSC+WISE mask, 0.5<z<1.0
* hpwm_unc_lrg_0510.cnt : cross-correlation between uncertain and lrg within the HSC+WISE mask, 0.5<z<1.0
* hpwm_unobscPu_lrg_0510.cnt : cross-correlation between unobscured+uncertain and lrg within the HSC+WISE mask, 0.5<z<1.0
* hpwm_obscPu_lrg_0510.cnt : cross-correlation between unobscured+uncertain and lrg within the HSC+WISE mask, 0.5<z<1.0
  

## TODO
---
* Need to aestimate good masses and photometry of the stellar host in order to create matched samples, specially relevant for type 1 AGN. SED fitting?


## DONE
---
* Added mask for HSC+WISE (spikes+halo+ghosts, no moon)
