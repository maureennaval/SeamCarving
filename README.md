# Seam Carving

A Java applet that implements the content-aware image resizing algorithm, Seam Carving, developed by Shai Avidan and Ariel Shamir for SIGGRAPH 2007

Link to the paper: http://www.eng.tau.ac.il/~avidan/papers/imretFinal.pdf

# Description of Algorithm

Seam carving finds the least noticeable “seam” (path in an image) from top to bottom. Repeatedly removing or adding seams allow for image-aware resizing. Implementing seam carving relies on how one quantifies the “least-noticeable” seam. 

The technical paper refers to the shortest path through the image, where distance is the total strength of the image edges traversed along the way. Paths are made up of pixels connected by an edge or corner. When resizing images, the algorithm chooses seams with the lowest energy path. The basic process of seam carving starts with the original image, then applying luminosity, finding the energy of luminosity, find the seam from the energy map, and then removing the seam.
