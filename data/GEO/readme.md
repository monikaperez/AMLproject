https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE129086 MV411 ATAC seq
https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71779 
https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71776
MV411 Pol2, BRD4, H3K79me2 Chips before/after inhibition of BRD4 DOT1L with SGC0946 IBET and SGC0946+IBET
https://www.ncbi.nlm.nih.gov/sra?term=SRP111133


http://epigenomegateway.wustl.edu/legacy/?genome=hg19&datahub=https://egg2.wustl.edu/web_portal_cache/1673283960.json 15 and 18 state models based on K562 CL chromatin marks (marks are used to create transition probability model and each transition represent an underlying state learnt based on the marks. Each region is under a specific HMM state. They can then be annotated by the state in which the model is at that location, given previous ones. In order to assign biologically meaningful mnemonics to the states, we compute the overlap and neighborhood enrichments of each state relative to various types of functional annotations (Fig. 4b-c,f, Extended Data 2b,c, Fig. S2).)
https://egg2.wustl.edu/roadmap/web_portal/

GSM3693109_MV411.rpkm.bw  ATACseq
MV411_SMC1_all_rep_duplicate_removed_allValidPairs.hic SMC1
MV411_H3K27ac_all_rep_duplicate_removed_allValidPairs.hic H3K27ac

GSE116256_RAW 35 samples of scRNAseq of AML at D0 and D14+ (chemoterapy) 16 patients and 5 healthy donor (bone marrow)

known enhancers to compare
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5467550/

## [Protein array, RRBS,ABSOLUTE CN, Translocation, miRNA, metabolomics] for MV411- ACH-000045

`CCLE_RPPA_20181003 = tc.get(name='depmap-rppa-1b43', version=3, file='CCLE_RPPA_20181003')`

`translocations = tc.get(name='translocations-b331', version=5, file='translocations')`

`CCLE_metabolomics_20190502 = tc.get(name='metabolomics-cd0c', version=4, file='CCLE_metabolomics_20190502')`

`CCLE_RRBS_cgi_CpG_clusters_20181119 = tc.get(name='rrbs-4b29', version=7, file='CCLE_RRBS_cgi_CpG_clusters_20181119')`

`CCLE_RRBS_enh_CpG_clusters_20181119 = tc.get(name='rrbs-4b29', version=7, file='CCLE_RRBS_enh_CpG_clusters_20181119')`

`CCLE_RRBS_tss_CpG_clusters_20181022 = tc.get(name='rrbs-4b29', version=7, file='CCLE_RRBS_tss_CpG_clusters_20181022')`

`CCLE_miRNA_20180525 = tc.get(name='mirna-expression-2c5f', version=3, file='CCLE_miRNA_20180525')`


## we have chip data for

- CD34
- D0
- D9
- EOL1
- F36P
- HEL
- HEL9217
- HL60
- Kasumi1
- KG1
- M6
- MOLM13
- MONOMAC6
- MV411
- NB4
- NOMO1
- OCIAML2
- OCIAML3
- P31FUJ
- PLB985
- SHI1
- SKNO1
- TF1
- THP1
- U937
- UCSDAML1
- UT7

## we have WGS for 

- EOL1
- EOL1_HAEMATOPOIETIC_AND_LYMPHOID_TISSUE
- HEL9217
- HEL9217_HAEMATOPOIETIC_AND_LYMPHOID_TISSUE
- MV411
- MV4-11_HAEMATOPOIETIC_AND_LYMPHOID_TISSUE
- THP1
- THP1_HAEMATOPOIETIC_AND_LYMPHOID_TISSUE

## we have ENCODE Data for

HL60 HL-60
THP1 THP-1


## we have deepbind for
'BRD4',
'CDK6',
'CEBPA',
'ELF2',
'FLI1', x
'GFI1',
'IKZF1', x
'IRF2BP2',
'IRF8', x
'LMO2',
'LYL1',
'MAX', x
'MEF2C', x
'MEF2D', x
'MEIS1', x
'MYB', x
'MYC', x
'RUNX1',
'RUNX2', x
'SPI1', x
'ZEB2',
'ZMYND8'

## Part of same expression cluster in RNP experiment 

### batch effect

MAX CEBPa ZEB2 

### Bio 

MYC BRD4 MEF2D CDK6 IRF2BP2
RUNX1 RUNX2 ZMYND8 SPI1
GFI1 FLY1 MYB IKZF1 ELF2 CEBPa MEIS1
ZEB2
LMO2 MAX LYL1 MEF2C

### diff expression

BRD4 CDK6 IRF2BP2 IRF8 MEF2D MYC RUNX1 RUNX2 SPI1 ZEB2 ZMYND8
CEBPa ZEB2
MYB
MAX MEF2C LYL1
LMO2
IKZF1 FLI1 ELF2 GFI1 MEIS1

### Date RNP
IRF2BP2	IDT	12/18/19
IRF8	IDT	12/18/19
MEF2D	IDT	12/18/19
MYC	IDT	12/18/19
RUNX1	IDT	12/18/19
RUNX2	IDT	12/18/19
SPI1	IDT	12/18/19
ZMYND8	IDT	12/18/19
CDK6	IDT	12/18/19
BRD4	IDT	12/18/19
Non-Target	IDT	12/18/19
LMO2	Synthego	4/9/19
LYL1	Synthego	4/9/19
MAX	Synthego	4/9/19
ZEB2	Synthego	4/9/19
MEF2C	Synthego	4/9/19
Non-Target	Synthego	4/9/19
MEIS1	Synthego	6/7/19
FLI1	Synthego	6/17/19
ELF2	Synthego	6/17/19
GFI1	Synthego	6/17/19
IKZF1	Synthego	6/17/19
CEBPa	Synthego	6/17/19
MYB	Synthego	7/16/19

