The supplementary material contains a set of files, the direct output of CREME, explaining the merging process.

This merging was done for the following chipseq:
| sample name | number of peaks |
|-|-|



we only had one replicate and were not able to use or tool for:

| ChIP name |
|-|
| SMC1 |
| PLAGL2 |
| MEIS1 |
| FLAG_GFI |
| FLAG_IRF2BP2 |
| LDB1 |
| H3K79me2 |
| GFI1 |
| H3K27me3 |
| HEX |
| FOSL2 |
| MYBL2 |
| CDK9 |
| H3K4me3 |
| FLI1 |
| MLL_KTM2A |
| RARA |
| AFF4 |
| CTCF |
| SREBP1 |
| H3K18 |
| E2F3 |
| CEBPB |
| H3K36me2 |
| PSER2 |
| TFP4 |
| STAT5B |
| FLAG_MEF2C |
| ZFP281 |
| LYL1 |
| H3K36me3 |
| H3K9ac |
| CDK13 |
| RXRA |
| FLAG_PU1 |
| H3K4me1 |

For the ones that had multiple replicates, merging produced the following merged TF peaks:

| ChIP name | # of peaks | # of merged samples | # of samples that were dropped | marked as low quality peak* |
|-|-|-|-|-|
| CEBPA | 165942 | 4 | 0 | N |
| ELF2 | 43324 | 2 | 0 | N |
| JUND | 3369 | 2 | 0 | Y |
| HOXA9 | 1313 | 2 | 0 | Y |
| IRF2BP2 | 10377 | 4 | 0 | Y |
| ETV6 | 7173 | 2 | 0 | Y |
| WDR5 | 939 | 5 | 0 | Y |
| H3K27ac | 171048 | 6 | 0 | N |
| RUNX1 | 61425 | 4 | 0 | N |
| FOXP1 | 46319 | 2 | 0 | N |
| GATA2 | 18108 | 1 | 1 | Y
| IKZF1 | 36200 | 2 | 0 | N |
| BRD4 | 51200 | 2 | 0 | N |
| SP1 | 26798 | 3 | 0 | N |
| PU1 | 106618 | 3 | 0 | N |
| LMO2 | 19024 | 2 | 0 | N |
| ZMYND8 | 23125 | 2 | 0 | N |
| MEF2D | 740 | 1 | 2 | N |
| MYC | 69049 | 5 | 0 | N |
| RUNX2 | 82572 | 4 | 0 | N |
| MAX | 77146 | 2 | 0 | Y |
| IRF8 | 70521 | 3 | 0 | N |
| GSE1 | 785 | 2 | 0 | Y |
| MYB | 26413 | 2 | 0 | N |
| ZEB2 | 9484 | 3 | 1 | N |
| MEF2C | 28498 |  |  | N |
| FLAG_MEF2D | 24413 | 4 | 0 | N |
| POLII | 56858 | 3 | 0 | N |
| MED1 | 35313 | 3 | 0 | N |

Merging failed for none of our samples. This is because of our decision to resequence more of the one ChIP replicates that had failed previously (MEF2C). Our rerun of that TF replicate merging can seen in the _retryMEF2C folder.

> The "ChIP name" represents a protein or mark that is pulled by the ChIP seq process.

---

_ded.txt_ explains the decision taken by CREME for each replicate to create its merging. More information about how those decisions are taken can be found in the _methods section_ or our _github page_.

For each ChIP name

---

The Venn Diagrams show the peak overlap between replicates.

each filename contains the ChIP name as well as additional label:
- the _before_ label in venn diagram's file name 
- the _recovered_ label in venn diagram's file name 

---

- the _new_found_peaks label in kdeplots
after_unique
before_unique

---

cdccc

after_pairplot
before_pairplot
