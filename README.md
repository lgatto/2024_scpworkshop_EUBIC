# Processing and analysing single-cell proteomics with the scp Bioconductor package

Mass spectrometry-based single-cell proteomics (SCP) has become a
credible player in the single-cell biology arena. Continuous technical
improvements have pushed the boundaries of sensitivity and throughput
to the point where high quality data sets are publicly
available. However, the computational efforts to support their
exploration, processing and analysis aren't widely available. The goal
of this workshop is to give participants the opportunity to learn how
to use the
[QFeatures](https://bioconductor.org/packages/release/bioc/html/QFeatures.html)
and
[scp](https://bioconductor.org/packages/release/bioc/html/scp.html)
Bioconductor package to manage, process and analyse single-cell
proteomics data. The hands-on workshop will start by introducing the
QFeatures class and its functions to perform generic proteomics data
analysis. We will then move to SCP and present how scp extends
QFeatures to single-cell applications. The remainder of the workshop
will be guide participants through the analysis of a real-life
analysis of published SCP data. This workshop is meant for users
familiar with R that want to learn current state-of-the-art SCP data
analysis.

Participants should install a recent version of R (version >= 4.3.1)
and run the following code chunk to install the necessary Bioconductor
packages:

```r
install.packages("BiocManager")
BiocManager::install(version = "3.18", ask = FALSE)
pkgs <- c("QFeaures", "SingleCellExperiment", "scp", "scpdata")
BiocManager::install(pkgs)
```

Workshop material and details will be available at
https://github.com/lgatto/2024_scpworkshop_EUBIC.
