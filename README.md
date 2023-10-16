# LowVertexFont
This GitHub repository contains Mathematica code for the generation of polygonal shapes representing letters of the alphabet. These polygons are derived from low-resolution rasterized fonts, where simple outlines are extracted from the pixelated letters. The resulting data is organized into three directories: whitebackground, nobackground, svgs.

The directory ./whitebackground contains the files 
  {"A.png", "B.png", ..., "Z.png"}.
They are all 256x256 png images.

The directory ./nobackground contains the files
  {"Anobackground.png", "Bnobackground.png", ..., "Znobackground.png"}.
They are all 256x256 png images, with transparent pixels instead of white pixels where there is no letter.

The directory ./svgs contains the files
  {"A.svg", "B.svg", ..., "Z.svg"}.
They are vector graphics whose viewBox's are slightly larger than the letters they contain.  The viewBox's are not consistent across files.

The letter shapes were created by rasterizing a font at very low resolutions, and extracting simple outlines from the very pixellated letters.
With the exception of {Y,R,I,K,Z,F,H,E,W,X,L}, the letters were rasterized at 9x9 pixels.
Y was rasterized at 14x14 pixels.
R was rasterized at 11x11 pixels.
I and K were rasterized at 10x10 pixels.
Z, F and H were rasterized at 8x8 pixels.
E, W and X were rasterized at 7x7 pixels.
L was rasterized at 6 pixels.
An illustration of this process can be seen in ./example.png, which contains the letter A rasterized at 9x9 pixels, and its extracted outline overlaid.

One nasty trick is (*2*) which circumvents BoundaryMeshRegion being AtomQ.
Another nasty trick (*1*) is the contour nesting code which assumes that contours with even depth are black (not 'inner') so may be treated as separate polygons.
