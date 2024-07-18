# goes-clouds
Comparisons of the [GOES-R](https://www.goes-r.gov/) ABI Cloud Mask product with in situ observations from [CUES](https://snow.ucsb.edu/)

---

## Functions/scripts:

### lw_clr.py

Functions for estimating clear-sky downward longwave radition and atmospheric emissivity. I'm using these here to compare against observations of all-sky downward longwave at the CUES site to identify periods of cloud cover (especially at night when we cannot use shortwave observations).

### cloud_detect.py

Detecting cloud cover using ground-based observations (similar to the clear-sky index of Marty & Philipona, 2000). First uses ground-based observations of air temperature and relative humidity to run an ensemble of clear-sky downward longwave (LWd) estimation methods (lw_clr.py). Then compares these estimates against LWd observations at the site. Where the LWd is greater than the clear-sky estimates, we likely have cloud-cover.

---

## Notebooks for testing/examples:

### test-lw-clr.ipynb

Testing the lw_clr.py functions.

### test-cloud-detect.ipynb

Testing the cloud_detect.py functions, and brute-force parameter test to find optimal clear-sky index thresholds. Read in [RESULTS.pkl](/misc/RESULTS.pkl) to get a pandas dataframe of the brute force parameter test results.

![cloud_detect_threshold_options.png](/images/cloud_detect_threshold_options.png "cloud_detect_threshold_options")

