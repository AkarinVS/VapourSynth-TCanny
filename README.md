Description
===========

Builds an edge map using canny edge detection.

Ported from AviSynth plugin http://bengal.missouri.edu/~kes25c/


Usage
=====

    tcanny.TCanny(clip clip[, float sigma=1.5, float t_h=8.0, float t_l=1.0, int mode=0, int op=1, float gmmax=50.0, int[] planes])

* clip: Clip to process. Any planar format with either integer sample type of 8-16 bit depth or float sample type of 32 bit depth is supported.

* sigma: Standard deviation of gaussian blur.

* t_h: High gradient magnitude threshold for hysteresis.

* t_l: Low gradient magnitude threshold for hysteresis.

* mode: Sets output format.
  * -1 = gaussian blur only
  * 0 = thresholded edge map (2^bitdepth-1 for edge, 0 for non-edge)
  * 1 = gradient magnitude map
  * 2 = edge pixel only gradient direction map (non-edge pixels set to 0)
  * 3 = gradient direction map

* op: Sets the operator for edge detection.
  * 0 = the operator used in tritical's original filter
  * 1 = the operator proposed by P. Zhou et al.
  * 2 = the Sobel operator
  * 3 = the Scharr operator

* gmmax: Used for scaling gradient magnitude into [0, 2^bitdepth-1] for mode=1.

* planes: A list of the planes to process. By default all planes are processed.
