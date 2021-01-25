# AML methods descriptions

## chipseq analysis

Chipseq analysis was done on raw fastq files, using nextflow's chipseq pipeline on hg38 reference genome. A forked vesion of the pipeline containing additional code to manage run on google cloud and drosophila spike-in was create in __github:jkobject/chipseq__. Chipseqs were a mix of paired end and single end. MACS2 broadpeak mode was used for: "CEBPB", "BRD4", "PU1", "MED1", "SMC1", "IRF2BP2", "CEBPA" and all histone proteins.
A list of samples used can be found in the [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U), under __Chip_Tracker_JK__ .
Notebooks, functions and versions can be found at __jkobject/AMLproject__.

## differential chipseq

Differential binding of the same protein under two conditions was computed using MACS2 __diffbdgpeak__ mode.
Scaling factors were computed using drosophila spike-in. The [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U) displays how scaling was computed for each differential chipseq samples.

The scaling values where used to rescale the actual scaling values from diffbdgpeak (see our python function).
Notebooks, functions and versions can be found at __jkobject/AMLproject__.

## merging replicates

We have had variable amount of chipseq replicates.
Some of them were described as bad after QC-ing them on our processing pipeline, using multiQC and visual inspection (see annotations in the [chip tracker](https://docs.google.com/spreadsheets/d/1yFLjYB1McU530JnLgL0QIMAKIkVl3kl0_LCHje2gk8U)).

From these we needed to compute a consensus peak profile for each TFs. We created a tool that computes the best consensus from a set of replicates. Using bad/good annotations, overlap information and recovering/reassessing peaks across replicates using the same algorithm as MACS2's.

## rnaseq analysis

For RNAseq analysis, we used the same pipeline as the one used by CCLE (Cancer Cell Line Encyclopedia): STAR+RSEM, with STAR v2.6.1c, RSEM v1.3.0 and gencode's v29 reference gene regions.
we used hg38 reference genome and regions, enriched with ERCC92's v29 reference
Notebooks, functions and versions can be found at __jkobject/AMLproject__.
Results were merged into a dataframe. Genes with no expression or no variance in expression were dropped.

### scaling factors

Scaling factors were computed using our ERCC spike-in. We used ERCC's R dashboard package to get QC on the spike in. We only scaled samples were ERCC displayed a mean scaling of at least 2x higher the standard error.

### differential expression analysis

For differential analysis we used DESeq2 v1.26.0. We defined

## slamseq analysis



## motif analysis

Motif analysis has been done using __MEME v5.1.1__ and the __HOCOMOCOv11_full_HUMAN_mono__ database of human motifs. the fasta file was a personalized genome of MV411 using hg38 fasta file and  mutations called by __Haplotype Caller__ on __CCLE__'s 30x WGS of MV411.
Motifs were called on MV411 using open region of the genome from our MV411 ATACseq data. Found motifs were merged into our consensus set of peaks from the cobinding matrix, if they were at most 100 bp from the peak.
