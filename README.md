# Data storage for "Understanding CMIP6 biases in the representation of the Greater Horn of Africa long and short rains"
Rainfall statistics, climatological circulation metrics, and correlations calculated for the research in Schwarzwald et al., upcoming.

## Structure of `all_stats.csv`
`all_stats.csv` contains all precipitation statistics, circulation metrics, and correlations calculated for "Understanding CMIP6 biases in the representation of the Greater Horn of Africa long and short rains" (_submitted_). 

The first two columns are indices:
- `model`: The name of the data source of the statistics. Items are either the name of a CMIP6 model, or "obs" for observations or reanalysis. For "obs", the source for precipitation statistics is CHIRPS, for SSTs, OISST, and for $u$ and $\omega$ ERA5. 
- `season`: Whether the statistic is calculated or refers to the 'long' or 'short' rains.

The next seven columns are statistics of the rainy seasons. They are all named "`pr_[statistic name]`". All statistics are calculated at the pixel level, and then averaged over every pixel in the study area (see paper Section 3.1 for details).
- `onset`: Season onset
- `demise`: Season demise
- `duration`: Season duration (onset - demise + 1)
- `peak_timing`: Day of peak rainfall 
- `peak_amount`: Amount of rainfall on peak day
- `integrated_amount`: Total amount of rainfall in a season 
- `seas_ratio`: The ratio of the 1st to the 2nd harmonic (necessarily < 1, since the study area is defined as all pixels where this ratio is < 1)

The next set of columns are the climatological circulation metrics $M_c$ (see Section S2) - "timing" of peak and "amount" for each model/obs, season. Columsn are named "`[varname]_[timing/amount]`" In addition to the variables used in the paper (WIOSSTs as "`tos`", Indian Ocean Dipole mode index as "`dmi`", $u$ as "`ua250`", $\omega$ as "`wap250`" for 250 hPa and "`wap500`" for 500 hPa), other variables listed include: 
- `hus1000`/`hus850`: 1000 hPa and 850 hPa specific humidity, respectively
- `mse1000`/`mse850`: 1000 hPa and 850 hPa moist static energy, respectively

The final set of columns are the calculated correlations $\rho^{IM,mod}$ and $\rho^{IO}$ (see Section S4). Column names are "`[varname]_[timing/ammount]_corr`". "Timing" correlations are the timing of the peak of a given variability and the timing of peak rainfall, "amount" correlations are the peak of the circulation variable and the total rainfall in a season.  
