### Questions we can answer with image analysis
1. signal intensity under different conditions of cells, tissues
2. number of cells in a field
3. characterization of tissues

- an image is just a matrix of numbers

## Pixels
Picture element
- they are basically tiny boxes that can be looked at as numbers when really zoomed in

Properties of image
- pixel size: width height and depth of the images (as individual squares)
- resolution: measure of how close objects can be in an image is called spatial resolution
- images are stored as bits in microscopy: 8,12,16 bits
    -- 8 bit images: 256 pixels (gray values; 0-255)

On the software
- look up tables: how image is displayed on the screen - pixel values to colors
    -- different LUK have different colors - gray, rgb, green etc; the image will be colored different but will have the same pixel value

Histogram
- basically summary of images

### Filters and segmentation

#### Filters
- Image processing filter: changes pixel values on the original Picture
- noise: unwanted modification of image
    -- dark noise: statistical variation of how many electrons are generated if a photon arrives in a camera pixel
    -- short noise: statistical variation of the photos arriving at the camera

    pixel intensity = target intensity + background + camera offset + noise

- kernal
    -- non linear filters- replace each pixel value with a linear combination of surrounding pixels; kernals are basically matrices numbers
    -- we can "convolve" and image with a kernal 

    ***** insert an image from your notes *****

    -- non linear filter- replace pixel value with non linear function (number)
    -- statistic filter: min, median, max, variance, std (these functions are applied to each pixel value)

- edge detection
    -- helpful while workign with structures that have bright and dark structures

### Math operations on images
- subtraction
    -- "subtract background" function helps extract background and remove background 
    -- "division" of image by background
    -- in cell, segmentation of nucleus can beb improved by subtracting a channel visualizing nuclei envelope from nuclei channel (subtracting images with different operations)

### Image segmentation
Steps for pre processing images
1. segmentation and labelling
    -- add filters, subtract background
    -- thresholding: seperation of regions from background-- this can be done by setting a min/max signal intensity as threshold
    ** apply same algorithm to all images
    -- over blurring to improve obejct detection and then threshold (if the og way of threshold doesnt work);  blur image, but process on the original image, not the blurred image. 

2. Refining mask 
    -- binary opening/closing: eg: a cell may have spots within which may have holes (diff pixel intesity), in such cases, binary masks maybe used to fill the holes
    -- erosion: every pixel with one black neighbor becomes black
    -- dilation: pixel with white neighbor becomes white
        - 8- connected neighborhood (Moore neighborhood)
        - 4- connected neighborhood (von- Neumann neighborhood)
    -- erosion and dilation can be combined for outline correction
    -- watershed: this alg cuts connected objects

    -- Connected component labelling: differentiatinf obejects 



