# Seam Carving

A Java applet that implements the content-aware image resizing algorithm, Seam Carving, developed by Shai Avidan and Ariel Shamir for SIGGRAPH 2007

Link to the paper: http://www.eng.tau.ac.il/~avidan/papers/imretFinal.pdf

# Description of Algorithm

Seam carving finds the least noticeable “seam” (path in an image) from top to bottom. Repeatedly removing or adding seams allow for image-aware resizing. Implementing seam carving relies on how one quantifies the “least-noticeable” seam. 

The technical paper refers to the shortest path through the image, where distance is the total strength of the image edges traversed along the way. Paths are made up of pixels connected by an edge or corner. When resizing images, the algorithm chooses seams with the lowest energy path. The basic process of seam carving starts with the original image, then applying luminosity, finding the energy of luminosity, find the seam from the energy map, and then removing the seam.

# Seam Carving Results

Photos with diagonal content render with visual artifacts. The following images with diagonal content:
- christmas_original.jpg: Seems that the result in the paper uses different types of energy (other than just forward energy like my implementation)
- Fuji.jpg: Seems that my implementation stops finding new seams after a certain cut-off point
- edo.jpg: The moon is the only one with visual artifacts. One solution could be to target the moon as a region to keep (I have not implemented such a feature).
- dolphin.jpg: The dolphin silhouette is not as smooth as the intended result but the water, sky, and horizon leave render without visual artifacts.

Photos that successfully render without visual artifacts.
- waterfall.jpg
- charles_original.jpg
- Okinawa.bmp

# Object Removal

A further extension of Seam Carving is the ability for the users to select certain content they wish to remove as well as selecting parts they wish to keep. My implementation only allows for removing a pre-highlighted region on the image. The user *can* paint over a regular image -- but the implementation only allows for painting one pixel at a time. So, it is best to load in an image with the target region to remove painted over with pure green.

# Object Removal Results

Image: Beach.jpg

Target region: Girl
- Result: Successful with no visual artifacts

Target: Pigeon
- Result: Almost successful -- there is a cluser of green pixels that were not removed
- Possible solutions: Create more accurate masks, ensure that the implementation read that there were no more leftover green pixels in the image, edit the green on Photoshop (would be easier than editing original image)

# Other
Total time spent on project: 49 hours

Possible extensions to this project: Implement bject removal interface (allow user to paint) for region to remove along with implementing target regions to keep.
