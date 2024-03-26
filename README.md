# Firehoods

Created by Douglas Radford
26/3/24

Please see the Firehoods.Rmd or Firehoods.html (which is generated from the R markdown, Rmd file) for details on the creation of this github.

Development notes:
	- We note that when a coarse resolution is used, the angles in the region of the point of interest become quite coarse (ie 45, 90, 135). 
		- As such, if using a coarse resolution and small alpha, many of these cells may be not considered in the weighting.
		- For this reason, we suggest not to use a coarse resolution where alpha is small (ie. alpha < 45). This advice is especially pertinent where using wind directions which are not on the cardinal or ordinal directions.
		+ One workaround is to use a polygon-based approach to defining the neighbourhood and using touches=T when rasterising. This method has been previously implemented - please contact Doug for further information if interested.
