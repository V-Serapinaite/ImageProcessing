1. Reads data
2. Finds regions of variation in each batch of images
  Simple approach was used to find variation areas in images:
  - 2 consecutive images were selected. Such approach was chosen since delta of parameter difference is around ~0.04 between images. This can indicate which vertices areas change with slight parameter modification.
  - magnitude of coordinates differences was calculated
  - outliers were identified and ignored
  - top 5 % with highest magnitude values were selected as variation coordinates
  - convex hull was created based on the coordinates
  - coordinate names were stored for later use


3. Correctly "draw" the change regions on the images from the "train set" folder
  - Coordinate names from previous cell are used to identify which coordinates belong to region of variation
  - Coordinates are adjusted based on current image - scaled down by 2 times, and y axis mirrored
  - Outliers are removed
  - Convex hull is created based on the coordinates and displayed on examples
