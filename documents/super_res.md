# Super res microscopy output's Methods

## input data

The data (available on our github project at: _https://github.com/jkobject/AMLproject/tree/master/data/micro\_Yaser3/_) is the output of the _"ZEN"_ algorithm on our super-resolution microscopy images. We used _"ZEN 3.0 Black"_ for image processing (channel alignment, SIM processing and image subsetting) and _ZEN 3.1 Blue_ for segmentation and data formating.
The segmentation algorithm has been trained on raw images labelled by hand. Images, as well as the trained algorithm are available at _ded_. To download the software, please visit: _https://www.zeiss.com/microscopy/int/products/microscope-software/zen.html#downloads_. More information about the code is available here: _https://github.com/zeiss-microscopy/OAD_.

## PostProcessing

The processing pipeline is available at _https://github.com/jkobject/AMLproject/tree/master/notebooks/Fish\_SuperRes.ipynb_ and uses genepy's fish toolkit _https://github.com/broadinstitute/genepy/tree/master/genepy/imaging/fish.py_.

A couple key algorithms are used:
1. One to aggregate each z stacks of each nuclei, transforming 2D dots (diskoids) into 3D dots (spheroids). The same algorithm will be used to define overlapping d
2. One to compute an enrichment metric for each experiment
3. One to make our 1D distance plots
4. One to make our 2D distance plots

### 1. the colocalization algorithm

the algorithm works by aggregating dots of the same color into a merged 3D dots when the distance between dots' center is less than average size of a dot. their size, signal, location also gets aggregated. Dots that only exist in one z stack get filtered out. If we see that red and green dots can be merged, we annotate them as being in co-localization. 

in plots where red dots are associated with a DNA loci. We only keep the first 3 biggest red dots. 


### 2. the enrichment

Enrichment is computed as a fisher's exact test between the expected number of red dots in green regions vs the actual measured number.

The expected number of red dots in the green region is computed by defining the total region of nucleus that contains green dots vs not. e.g. if 20% of the nucleus is covered by green dots and we know we have 3 red dots, we would expect that by chance 0.6 red dots would be in co-localization.

The actual number is defined as the number of co-localizing red dots vs non-co-localizing red dots.

### 3. 1D distance plot

All of our plots were made using seaborn. In the 1D distance plot was made by looking at all dots around a red dot. the values over each distance bins were computed by summing over all dot's signal in that region. Each bin was then scaled by distance following an RBF function. The scale was according to the total volume of each region the bin was summing over. The goal was to account for the variable size of each bins, as the further one gets from the center the larger the regions/bins get.

### 4. 2D distance plots

In this plot type, the intensity represents a (gaussian) kernel density estimation across the green dots. This was done over all zstacks of a cubic region of 1400nm by sides centered around each red dots, across all nuclei in that experiment.

Each density is weighted by the average green signal intensity of each green dot. Each plot's density is then scaled by the mean green signal difference in between the DMSO and VHL plot.
