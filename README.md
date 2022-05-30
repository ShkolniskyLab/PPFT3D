# PPFT3D - Three-dimensional pseduo-polar Fourier transform and three-dimensional discrete Radon transform

# Content
The package contains functions for computing the 
1.	3D forward and inverse pseudo-polar Fourier transform
2.	3D forward and inverse discrete Radon transform


The package contains implementations of three inversion algorithms for the pseudo-polar Fourier transform:
1.	A reference iterative implementation, described in the paper "A. Averbuch and Y. Shkolnisky. 3D Fourier based discrete Radon transform. Applied and Computational Harmonic Analysis, 15(1):33-69, 2003."
2.	A fast inversion, described in "Fast convolution based inversion of the pseudo-polar Fourier transform”, Y. Shkolnisky and S. Golubev, preprint.
3.	A GPU implementation of the code in 2. 
4.	An implementation of a direct inversion, described in “A. Averbuch, G. Shabat and Y. Shkolnisky. Direct inversion of the 3D pseudo polar Fourier transform. SIAM Journal on Scientific Computing, 38 (2), A1100-A1120, 2016” (Highlights: running time independent of the input, no convergence criterion is required by the algorithm).

# Installation
1.	Compile MEX files: 
    * From MATLAB, `cd` to the directory into which you have extracted the package
    * Run the script `makemex`
    * Note that this script should be executed only once to compile MEX files
2.	Every time you want to use the package, run first the script `initpath`

# Directory structure
1.	refcode – Reference code for the 3D pseudo-polar Fourier transform. The functions in this directory are implemented exactly as described in the paper “A. Averbuch and Y. Shkolnisky. 3D Fourier based discrete Radon transform. Applied and Computational Harmonic Analysis, 15(1):33-69, 2003”, without any optimizations.
2.	fastinv – Fast convolution based inversion of the pseudo-polar Fourier transform.
3.	gpu - GPU implementation of the code in fastinv.
4.	common – Files that are common to the various routines
5.	tests – Various functions to test the accuracy and speed of the forward and inverse transforms.

# Important functions
Note that all functions are documented using MATLAB style documentation
* `ppft3`	Forward 3D pseudo-polar Fourier transform
* `ippft3`	Inverse 3D pseudo-polar Fourier transform
* `PtP3`	The gram operator of the preconditioned pseudo-polar Fourier transform, namely a consecutive application of the forward transform followed by its preconditioned adjoint
* `fippft3` Fast inverse pseudo-polar Fourier transform
* `fippft3_gpu` GPU implementation of `fippft3`
 
# References
1. A. Averbuch and Y. Shkolnisky. 3D Fourier based discrete Radon transform. Applied and Computational Harmonic Analysis, 15(1):33-69, 2003
2. A. Averbuch, G. Shabat, and Y. Shkolnisky. Direct inversion of the 3D pseudo-polar Fourier transform. SIAM Journal on Scientific Computing 38(2): A1100-A1120, 2016
