# AML methods descriptions

## chipseq analysis

Chipseq analysis was done on raw fastq files, using nextflow's chipseq pipeline on hg38 reference genome. A forked version of the pipeline containing additional code to manage run on google cloud and drosophila spike-in was create in [jkobject/chipseq](https://github.com/jkobject/chipseq/). Chipseqs were a mix of paired end and single end. MACS2 broadpeak mode was used for: "BRD4", "MED1", "IRF2BP2", and all histone proteins.
A list of samples used can be found in the [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U), under _Chip\_Tracker\_JK_ .
Notebooks, functions and versions can be found at [jkobject/AMLproject](https://github.com/jkobject/AMLproject/).

## super enhancer calling

For super enhancer calling we used the [ROSE2](https://github.com/jkobject/rose) algorithm (which for now only work on python2), on each of our H3K27ac ChIP)-seq replicates and then merging the output bed files using genepy’s ded function with a merging window of __1000__.

## TF co-occupancy map

To compute a TF co-occupancy map we used [genepy](https://github.com/broadinstitute/genepy/blob/master/genepy/epigenetics/chipseq.py)'s _simpleMergePeaks_ function on all of our sample's bed files. It takes the union of all peaks and merge peaks at most 150 bp away from one another. This consensus bed file contains aa signal intensity column for every samples. The signal is 0 when there is no peak.

## differential chipseq

Differential binding of the same protein under two conditions was computed using [MACS2 diffbdgpeak](https://github.com/macs3-project/MACS/wiki/Call-differential-binding-events) mode.
Scaling factors were computed using drosophila spike-in. The [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U) displays how scaling was computed for each differential chipseq samples.

The scaling values where used to rescale the actual scaling values from MACS2 (see [our _fullDiffPeak_ function](https://github.com/broadinstitute/genepy/blob/master/genepy/epigenetics/chipseq.py#L560)).
Notebooks, functions and versions can be found at [jkobject/AMLproject](https://github.com/jkobject/AMLproject/).

## merging replicates

We have had variable amount of chipseq replicates.
Some of them were described as bad after QC-ing them on our processing pipeline, using [multiQC](https://multiqc.info/) and visual inspection (see annotations in the [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U)).

From these we needed to compute a consensus peak profile for each TFs. We created a tool: CREME, that computes the best consensus from a set of replicates. Using bad/good annotations, overlap information and recovering/reassessing peaks across replicates using the same algorithm as [MACS2](https://github.com/macs3-project/MACS)'s.

Information on the results of CREME can be found [here](https://github.com/broadinstitute/genepy/blob/master/genepy/epigenetics/CREME.md).

Notebooks, functions and versions can be found at [jkobject/AMLproject](https://github.com/jkobject/AMLproject/).

## rnaseq analysis

For RNAseq analysis, we used the same pipeline as the one used by CCLE (Cancer Cell Line Encyclopedia): __STAR__+__RSEM__, with __STAR__ v2.6.1c, __RSEM__ v1.3.0 and __gencode__'s v29 reference gene regions.
we used hg38 reference genome and regions, enriched with ERCC92's v29 reference.
Notebooks, functions and versions can be found at [jkobject/AMLproject](https://github.com/jkobject/AMLproject/).
Results were merged into a dataframe. Genes with no expression or no variance in expression were dropped.

### scaling factors

Scaling factors were computed using our __ERCC__ spike-in. We used __ERCC__'s R dashboard package to get QC on the spike in. We only scaled samples were __ERCC__ displayed a mean scaling of at least 2x higher the standard error.

### differential expression analysis

For differential analysis we used __DESeq2__ v1.26.0. We defined a simple formula of ~ Control + Condition. We used __ERCC__ pseudo genes to rescale, by passing them to __DESeq2__'s `run_estimate_size_factors` control_genes parameter.

## slamseq analysis

slamseq processing was performed by using __slamdunk__, a modified debugged [version](https://github.com/jkobject/slamdunk.com), that could work on python3, with both single & paired end sequencing an with mapping to ERCC genome. We then removed genes with either no expression or no variance in both tc count and total count files.

For differential analysis we used __DESeq2__ v1.26.0 on tccounts, taking the total counts as scaling factors. We did so by passing the mean expression of the genes across each experiments to __DESeq2__'s `run_estimate_size_factors` geoMeans parameter. We used __ERCC__ pseudo genes to directly rescale __DESEq2__'s computed size factors using its `getSizeFactors` and `setSizeFactors` functions.

## motif analysis

Motif analysis has been done using __MEME v5.1.1__ and its __HOCOMOCOv11_full_HUMAN_mono__ database of human motifs. the fasta file was a personalized genome of MV411 using hg38 fasta file and  mutations called by __Haplotype Caller__ on __CCLE__'s 30x WGS of MV411.
Motifs were called on MV411 using open region of the genome from our MV411 ATACseq data. Found motifs were merged into our consensus set of peaks from the cobinding matrix, using [genepy](https://github.com/broadinstitute/genepy/blob/master/genepy/epigenetics/chipseq.py)'s _simpleMergePeaks_ function, merging any motifs at most 100bp away from a peak and dropping any motif not overlapping (i.e. merged) with a peak in the cobinding matrix.
