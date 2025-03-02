# WISEAGN-HSC-xcross
---
This contains the files, codes and notebooks to select AGN, classifiy, filter, and perform crosscorrelations between WISE AGN and HSC galaxies. Note this repo contains only the small data files. Any input file not present here is available in the shared google drive folder.

### gmm_split.ipynb
This implements a log-normal mixture model to separate between obscured/unobscured. Theres is a threshold to separate objects with uncertain classifitation into a third class. To run this notebook you need C75_hscmatched2arcs_wisematched2arcs.fits, which is Google Drive

### wiseagn_cross_hsc.ipynb
This notebook has two parts: the first one is to select various subsamples of AGN, plus the galaxies, plus the randoms. The second actually calculates the CCFs and generate plots. To run you need the AGN catalog with classifications C75_gmmclass.parquet (ouput by gmm_split.ipynb), masked_hscx_c_gal.parquet (the HSC galaxies), and rands100_1.fits (a big pool of 100mill randoms for HSC galaxies). I have put these files in Google Drive.

### CNT files
These are the ouput cnt files that Gundam produces for each correlation run. You can plot directly from these. Check the names in wiseagn_cross_hsc.ipynb to associate each run to its sample.




## TODO
---
* Need to add a proper mask for WISE, as explained in the document
