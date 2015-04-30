# A Two-Continua Approach to Eulerian Simulation of Water Spray #
![http://cs.au.dk/~bang/spray_teaser.png](http://cs.au.dk/~bang/spray_teaser.png)

**LINK TO SOURCE CODE AT THE BOTTOM OF THIS PAGE**

Please read the README section before proceeding.

## Paper ##
http://cs.au.dk/~bang/publications/nielsen-siggraph2013-spray.pdf

## Video ##
http://cs.au.dk/~bang/publications/nielsen-siggraph2013-spray.mov

## README ##

This source code accompanies the paper "A Two-Continua Approach to Eulerian Simulation of Water Spray" by Michael B. Nielsen and Ole Østerby, published in ACM Transactions on Graphics 32(4), July 2013 as part of the SIGGRAPH 2013 Proceedings. The release contains a reference implementation of the spray simulation algorithm proposed and used to produce all examples in the paper. The code comes with XML parameter files that can be used to re-produce all spray simulations shown in the paper and the video.

Please cite our paper in case you use the source code to produce examples for a paper of your own.

This distribution contains source code previously released under the BSD license:
  * The Dynamic Tubular Grid (DT-Grid), used in the papers:
    * "Dynamic Tubular Grid: An Efficient Data Structure and Algorithms for High Resolution Level Sets", Nielsen and Museth, Journal of Scientific Computing, 2006
    * "Finite Elements on Very Large Dynamic Tubular Grid Encoded Implicit Surfaces", Nemitz,Nielsen,Rumpf,Whitaker, SIAM Journal of Scientific Computing, 2009
  * A Multi-Grid solver used in the papers:
    * "Guiding of Smoke Animations through Variational Coupling of Simulations at Different Resolutions", Nielsen,Christensen,Zafar,Roble,Museth, SCA 2009
    * "Improved Variational Guiding of Smoke Animations", Nielsen and Christensen, Eurographics 2010

The source code has been compiled with Visual C++ 8.0 (Visual Studio 2005) on Windows Vista. If you manage to get the code compiling on other platforms/with other compilers and would like to contribute back to this project, please let me know.

The source code depends on the following third party libraries:
  * The cephes math library (hypergeometric functions): http://www.moshier.net/cephes28.zip (a version including a visual studio project file is downloadable from this Google code page and must be placed in the External directory. Note that this is re-distributed under a different license.)
  * The vortex particle implementation from the paper "Synthetic Turbulence using Artificial Boundary Layers" by T. Pfaff, N. Thuerey, A. Selle, M. Gross: http://graphics.ethz.ch/Downloads/Publications/Papers/2009/Pfa09/Pfa09_code.tar.gz (a slightly modifed version required for the spray solver is downloadable from this Google code page and must be placed in the External directory (my edits are pre-fixed by MBN). Note that this is re-distributed under the GPL V2 license.).
  * Boost: http://www.boost.org/ and http://www.boostpro.com/download/ (we used version 1.43)
  * zlib: http://zlib.net/ (we used version 1.2.3)
  * Intel Math Kernel Library: http://software.intel.com/en-us/intel-mkl (we used version 10.1.0.018)
  * Intel Thread Building Blocks: http://threadingbuildingblocks.org/ (we used version 2.1)
  * Xerces XML parser: http://xerces.apache.org/xerces-c/ (we used version 2.8.0)
  * OpenGL, GLU, Glut: http://www.opengl.org/resources/libraries/
To properly link to these libraries you must set TBB21\_INSTALL\_DIR to point to the TBB installation directory and set include and library paths for the remaining libraries in Tools->Options->Projects and Solutions->VC++ Directories.

To get started:
  1. Download and install the required libraries. Next compile the source code in release mode in both the x64 and win32 configurations. Executables will be copied into the bin directory.
  1. Run the spray solver. For example, to re-produce the simulation in figure 8.b:
    1. `cd Examples`
    1. `../bin/x64_TwoContinuaSpraySolver.exe SpraySolverParams_waterfall_figure8b_res256_SPRAY.xml > waterfall_figure8b/waterfall_figure8b_res256/log.txt`
  1. The spray solver will generate a number of density fields. To visualize the results, start the simple viewer: `../bin/DensityFieldViewer.exe`
  1. To visualize a density field, type 'l' and type the name of the density field in the command prompt, for example: `waterfall_figure8b/waterfall_figure8b_res256/spray.SmokeDensity00150.df`
  1. To navigate the camera:
    * Left mouse button: Rotate
    * Right mouse button: Dolly/zoom (up: zoom out, down: zoom in)
    * Right mouse button + ctrl: translate in image plane
  1. For additional available commands, press 'h'.

## Google Drive Source Code Download (does not work in IE, use Google Chrome) ##

https://drive.google.com/folderview?id=0B2boehi83QGqajZwMEp4cTdNUms&usp=sharing

## Contact ##
Thanks for downloading the source code - I hope you find it useful.

Michael B. Nielsen,
Email: nielsenmb@gmail.com

## Acknowledgements ##
Thanks to Anders Brodersen and Brian Bunch Christensen for contributing to various parts of the source code as part of previous collaborations.