# Single-cell mapping of progressive fetal-to-adult transition in human hematopoiesis

Daniel Bunis, Yelena Bronevetsky, Elisabeth Krow-Lucal, Nirav R. Bhakta, Charles C. Kim, Srilaxmi Nerella, Norman Jones, Ventura F. Mendoza, Yvonne J. Bryson, James E. Gern, Rachel L. Rutishauser, Chun Jimmie Ye, Marina Sirota, Joseph M. McCune, Trevor D. Burt.

---

This repository is a companion to a study that is currently submitted for publication. GEO accession numbers for the data will be added once available. The data, both raw and processed, will also be available on figshare at <https://figshare.com/projects/Single-cell_mapping_of_progressive_fetal-to-adult_transition_in_human_hematopoiesis/76143>.

Pre-print manuscript is available at https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3569532.

## Current citation:

Daniel Bunis, Yelena Bronevetsky, Elisabeth Krow-Lucal, Nirav R. Bhakta, Charles C. Kim, Srilaxmi Nerella, Norman Jones, Ventura F. Mendoza, Yvonne J. Bryson, James E. Gern, Rachel L. Rutishauser, Chun Jimmie Ye, Marina Sirota, Joseph M. McCune, Trevor D. Burt. "Single-cell mapping of progressive fetal-to-adult transition in human naive T cells," manuscript in process, 2020.

## To use this code

1. Clone this repository
2. Download raw data from GEO or figshare.
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

### Session info

<details><summary>Click to show/hide</summary>
<p>

```
R version 3.6.2 Patched (2020-01-13 r77669)
Platform: x86_64-apple-darwin15.6.0 (64-bit)
Running under: macOS Mojave 10.14.6

Matrix products: default
BLAS:   /System/Library/Frameworks/Accelerate.framework/Versions/A/Frameworks/vecLib.framework/Versions/A/libBLAS.dylib
LAPACK: /Library/Frameworks/R.framework/Versions/3.6/Resources/lib/libRlapack.dylib

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] parallel  stats4    stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] org.Hs.eg.db_3.10.0         AnnotationDbi_1.48.0        clusterProfiler_3.14.3     
 [4] rtracklayer_1.46.0          dplyr_0.8.4                 slingshot_1.4.0            
 [7] princurve_2.1.4             SingleR_1.0.5               reticulate_1.13            
[10] pROC_1.16.1                 feseR_0.2.0                 ranger_0.12.1              
[13] caret_6.0-85                lattice_0.20-40             GEOquery_2.54.1            
[16] limma_3.42.2                ggrepel_0.8.1               reshape2_1.4.3             
[19] plyr_1.8.5                  eulerr_6.0.0                MAST_1.12.0                
[22] SingleCellExperiment_1.8.0  Seurat_3.1.3                DESeq2_1.26.0              
[25] SummarizedExperiment_1.16.1 DelayedArray_0.12.2         BiocParallel_1.20.1        
[28] matrixStats_0.55.0          Biobase_2.46.0              GenomicRanges_1.38.0       
[31] GenomeInfoDb_1.22.0         IRanges_2.20.2              S4Vectors_0.24.3           
[34] BiocGenerics_0.32.0         dittoSeq_0.3.0              ggplot2_3.2.1              

loaded via a namespace (and not attached):
  [1] rappdirs_0.3.1                ModelMetrics_1.2.2.1          tidyr_1.0.2                  
  [4] acepack_1.4.1                 bit64_0.9-7                   knitr_1.28                   
  [7] irlba_2.3.3                   multcomp_1.4-12               data.table_1.12.8            
 [10] rpart_4.1-15                  RCurl_1.98-1.1                generics_0.0.2               
 [13] metap_1.3                     cowplot_1.0.0                 TH.data_1.0-10               
 [16] RSQLite_2.2.0                 RANN_2.6.1                    europepmc_0.3                
 [19] future_1.16.0                 bit_1.1-15.2                  enrichplot_1.6.1             
 [22] mutoss_0.1-12                 httpuv_1.5.2                  xml2_1.2.2                   
 [25] lubridate_1.7.4               assertthat_0.2.1              viridis_0.5.1                
 [28] gower_0.2.1                   xfun_0.12                     hms_0.5.3                    
 [31] promises_1.1.0                progress_1.2.2                dbplyr_1.4.2                 
 [34] caTools_1.18.0                igraph_1.2.4.2                DBI_1.1.0                    
 [37] geneplotter_1.64.0            htmlwidgets_1.5.1             purrr_0.3.3                  
 [40] backports_1.1.5               annotate_1.64.0               gbRd_0.4-11                  
 [43] RcppParallel_4.4.4            vctrs_0.2.2                   ROCR_1.0-7                   
 [46] abind_1.4-5                   withr_2.1.2                   ggforce_0.3.1                
 [49] triebeard_0.3.0               checkmate_2.0.0               sctransform_0.2.1            
 [52] GenomicAlignments_1.22.1      prettyunits_1.1.1             mnormt_1.5-6                 
 [55] cluster_2.1.0                 DOSE_3.12.0                   ExperimentHub_1.12.0         
 [58] ape_5.3                       lazyeval_0.2.2                crayon_1.3.4                 
 [61] genefilter_1.68.0             recipes_0.1.9                 pkgconfig_2.0.3              
 [64] tweenr_1.0.1                  nlme_3.1-144                  nnet_7.3-12                  
 [67] rlang_0.4.4                   globals_0.12.5                lifecycle_0.1.0              
 [70] sandwich_2.5-1                BiocFileCache_1.10.2          rsvd_1.0.3                   
 [73] AnnotationHub_2.18.0          polyclip_1.10-0               lmtest_0.9-37                
 [76] Matrix_1.2-18                 urltools_1.7.3                zoo_1.8-7                    
 [79] base64enc_0.1-3               ggridges_0.5.2                png_0.1-7                    
 [82] viridisLite_0.3.0             bitops_1.0-6                  KernSmooth_2.23-16           
 [85] Biostrings_2.54.0             DelayedMatrixStats_1.8.0      blob_1.2.1                   
 [88] stringr_1.4.0                 qvalue_2.18.0                 readr_1.3.1                  
 [91] jpeg_0.1-8.1                  gridGraphics_0.4-1            scales_1.1.0                 
 [94] memoise_1.1.0                 magrittr_1.5                  ica_1.0-2                    
 [97] gplots_3.0.1.2                bibtex_0.4.2.2                gdata_2.18.0                 
[100] zlibbioc_1.32.0               compiler_3.6.2                lsei_1.2-0                   
[103] RColorBrewer_1.1-2            plotrix_3.7-7                 fitdistrplus_1.0-14          
[106] Rsamtools_2.2.2               XVector_0.26.0                listenv_0.8.0                
[109] pbapply_1.4-2                 htmlTable_1.13.3              Formula_1.2-3                
[112] MASS_7.3-51.5                 tidyselect_1.0.0              stringi_1.4.6                
[115] yaml_2.2.1                    GOSemSim_2.12.0               locfit_1.5-9.1               
[118] latticeExtra_0.6-29           grid_3.6.2                    fastmatch_1.1-0              
[121] tools_3.6.2                   future.apply_1.4.0            rstudioapi_0.11              
[124] foreach_1.4.8                 foreign_0.8-75                gridExtra_2.3                
[127] prodlim_2019.11.13            farver_2.0.3                  Rtsne_0.15                   
[130] ggraph_2.0.1                  digest_0.6.24                 rvcheck_0.1.7                
[133] BiocManager_1.30.10           shiny_1.4.0                   lava_1.6.6                   
[136] Rcpp_1.0.3                    later_1.0.0                   BiocVersion_3.10.1           
[139] RcppAnnoy_0.0.14              httr_1.4.1                    npsurv_0.4-0                 
[142] Rdpack_0.11-1                 colorspace_1.4-1              XML_3.99-0.3                 
[145] splines_3.6.2                 uwot_0.1.5                    sn_1.5-5                     
[148] graphlayouts_0.5.0            multtest_2.42.0               ggplotify_0.0.4              
[151] plotly_4.9.2                  xtable_1.8-4                  jsonlite_1.6.1               
[154] tidygraph_1.1.2               timeDate_3043.102             ipred_0.9-9                  
[157] R6_2.4.1                      TFisher_0.2.0                 Hmisc_4.3-1                  
[160] mime_0.9                      pillar_1.4.3                  htmltools_0.4.0              
[163] fastmap_1.0.1                 glue_1.3.1                    BiocNeighbors_1.4.1          
[166] interactiveDisplayBase_1.24.0 class_7.3-15                  codetools_0.2-16             
[169] fgsea_1.12.0                  tsne_0.1-3                    mvtnorm_1.0-12               
[172] tibble_2.1.3                  numDeriv_2016.8-1.1           curl_4.3                     
[175] leiden_0.3.3                  gtools_3.8.1                  GO.db_3.10.0                 
[178] survival_3.1-8                munsell_0.5.0                 DO.db_2.9                    
[181] GenomeInfoDbData_1.2.2        iterators_1.0.12              gtable_0.3.0   
```

</p>
</details>
