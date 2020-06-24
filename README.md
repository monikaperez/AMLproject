# AMLproject
We are working on the AML [pedDep]() project with [DFCi]() &amp; the [BroadInsitute](); [BCH](), looking at [CRCs]() and their relation to genomic dependencies in the context of [MLL/AML]().


link to the first paper on the role of the CRC in childhood cancer:
link to the second paper on :
link to the third paper on :

## Data

### ChipSeq data:

ChipSeq MV411 max data:
Chipseq other cell lines max data:
Chipseq IRF2BP2 spike ins:

### RNAseq data

slamseq JQ1.. max data:
slamseq RNAseq max data:
RNPv1:
RNPv2:

### others 

Promoters: were selected from https://epd.epfl.ch/get_promoters.php
slamseq paper data:
ATACseq data: https://www.ncbi.nlm.nih.gov/sra?term=SRX5608489
depmap data:
adjacency data:
ABC assignements data:
superenhancer matrix data:
Fish SuperRes data:


### For data access:


## Code

terra's RNAseq pipeline:
nextflow's ChIPseq:
nextflow's ATACseq:

### Code additionals: 

JKBio: 

	JKBio's epigenetics/ChIP_helper.py:


and ccle_processing


### AMLproject code:

- notebooks:
 - 
- html_notebooks:
	- ChIP_analysis_step_2.html
  - Fish_SuperRes.html
  - IRF2BP2 ChIPs Analysis.html
  - JQ1_RNA_analysis-v2.html
  - MOLM13notebook
  - plot with K562
  - RNA_RNP_analysis_v2-SCALING.html
  - RNA_RNP_analysis_v2.html
  - RNP_v2.1.html
  - slamRNA_analysis.html
  - slamseq IRF2BP2 degraded second run v2.html
  - slamseq IRF2BP2 degraded second run.html
  - slamseq IRF2BP2 degraded_v2.html
  - slamseq_MYCpaper.html
  - slamseq_MYCpaperMOLM13.html
  - slamseq-paper MYC degraded.html
- data:
 - CRIPSR_guides
 - enhancer-gene-assignment
 - ERCC92
 - genesets
 - GEO
 - RNP
 - slamseq
 - superenhancer
 - others
- results:
 - RNPv2
 - RNPv1
 - IGVsessions
 - IRF2BP2_CHIPdata
 - CRIPSR_guides
 - cobinding
 - slamseq Muhar paper
 - slamseq JQ1
 - slamseq 
- src:
	- ROSE:
	- ChromHMM
  - Ken's code
  	- code for the ABC mapping
  	- code for the inference of CRC members from RNAseq
  - Moe's code
  	- code for the plots
  	- code for the cell line/tumors relationship
  - Code to create the super enhancer matrix
  - Andrew's code
  	- Andrew's presentation
  - Neekesh's code to create the first CRC list

## TODO:

- packages for ccle_processing
- packages for JKBio
- packages for AMLproject
- add Ken's code to AMLproject