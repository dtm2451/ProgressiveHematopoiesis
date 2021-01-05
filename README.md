# Single-cell mapping of progressive fetal-to-adult transition in human naive T cells

This repository is a companion to a study of human naive T cells, classical monocytes, and hematopoietic progenitors. Code is available here. Transcriptome data is available through GEO (GSE158493; RNAseq counts / microarray transformed intensities only) and figshare ([link](https://figshare.com/projects/Single-cell_mapping_of_progressive_fetal-to-adult_transition_in_human_hematopoiesis/76143); counts / intensities & fully processed objects).

If you use this repository, we ask that you cite the paper:

---

Bunis, D. G., Bronevetsky, Y., Krow-Lucal, E., Bhakta, N. R., Kim, C. C., Nerella, S., Jones, N., Mendoza, V. F., Bryson, Y. J., Gern, J. E., Rutishauser, R. L., Ye, C. J., Sirota, M., McCune, J. M., & Burt, T. D. (2021). Single-Cell Mapping of Progressive Fetal-to-Adult Transition in Human Naive T Cells. Cell Reports, 34(1). https://doi.org/10.1016/j.celrep.2020.108573

### To use this code

1. Clone this repository
2. Download raw data from GEO (GSE158493) or figshare [link](https://figshare.com/projects/Single-cell_mapping_of_progressive_fetal-to-adult_transition_in_human_hematopoiesis/76143).
3. Extract and organize data in to your local copy of the repository with the below structure. (If you downloaded the pre-processed versions from figshare, place them in the root directory to use them directly with the `comparison.Rmd`.)
4. Use the .Rproj file to open an R project with this root directory as its base.

```
ProgressiveHematopoiesis/
|- bulkRNAseq_CD4naiveTcells.Rmd
|- comparison_between_datasets.Rmd
|- microarray-and-qRTPCR_CD4naiveTcells-and-monocytes.Rmd
|- ProgressiveHematopoiesis.Rmd
|- scRNAseq_HSPCs.Rmd
|- scRNAseq_naiveTcells.Rmd
\- bulkRNAseq_CD4s/
   (unzipped bulk naive CD4 RNAseq data)
   |- bulkCD4_counts.txt
\- HSPCs/
   (unzipped HSPCs scRNAseq raw and annotation data)
   \- cellranger_Raw/
      |- barcodes.tsv
      |- genes.tsv
      |- matrix.mtx
   \- Demuxlet/
      |- HSPC.best
\- Microarray_annotatedData/
   (unzipped microarray data)
   |- 17_medGen_longAnn_Tcells.csv
   |- 17_medGen_longAnn_Mono.csv
\- Tcells/
   (unzipped naive T cells scRNAseq raw and annotation data)
   \- cellranger_Raw/
      |- barcodes.tsv
      |- genes.tsv
      |- matrix.mtx
   \- Demuxlet/
      |- CD4.best
      |- CD4-8.best
      |- CD8.best
```
