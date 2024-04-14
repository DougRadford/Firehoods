# Firehoods

Created by Douglas Radford
26/3/24

This is a simple repository contining the neighbourhood function which can be used to quantify wildfire likelihood (Radford et al. 2024).
The referenced publication details the theory underpinning the use of neighbourhoods to infer wildfire likelihood.
We ask that where this package is used, the below publication is referenced as appropriate. 

The function established in this package creates a set of neighbourhoods based on parameters (alpha, distance & RF, see Radford et. al. 2024) and uses these neighbourhoods to aggregate a set of pre-defined raster properties (e.g., Rate of Spread).

The function is built using the terra, R package (Hijmans 2022). 

You can install this pacakge using the following code:
	install.packages("devtools")
	library(devtools)
	install_github("DougRadford/Firehoods")	


Radford, DAG, Maier, HRM, van Delden, H, Zecchin, AZ, Jeanneau, A (2024) 'An efficient, multi-scale neighbourhood index to quantify wildfire likelihood'. The International Journal of Wildland Fire. DOI: 10.1071/WF23055

Hijmans, R (2022) 'terra: Spatial Data Analysis. R package version 1.6-41.' Available at https://CRAN.R-project.org/package=terra [Accessed 18 November 2022].


Development notes:
	- We note that when a coarse resolution is used, the angles in the region of the point of interest become quite coarse (ie 45, 90, 135). 
		- As such, if using a coarse resolution and small alpha, many of these cells may be not considered in the weighting.
		- For this reason, we suggest not to use a coarse resolution where alpha is small (ie. alpha < 45). This advice is especially pertinent where using wind directions which are not on the cardinal or ordinal directions.
		+ One workaround is to use a polygon-based approach to defining the neighbourhood and using touches=T when rasterising. This method has been previously implemented - please contact Doug for further information if interested.
	- We aim to incorporate this function into the focalMat function within terra, at which point this package will become defunct. 