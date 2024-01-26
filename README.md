# Processing and analysing single-cell proteomics with the scp Bioconductor package

## Abstract

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

## Installation instructions

Participants should install a recent version of R (version >= 4.3.1)
and run the following code chunk to install the necessary
dependencies:

```r
install.packages(c("BiocManager", "remotes"))
BiocManager::install(version = "3.18", ask = FALSE)
pkgs <- c("QFeatures", "SingleCellExperiment", "scp", "scpdata",
          "ggplot2", "dplyr", "patchwork", "scater")
BiocManager::install(pkgs)
```

For the second part, also run the following command to install the
*scplainer* modelling code (pull request 50):

```r
BiocManager::install("UCLouvain-CBIO/scp#50")
```

NB: Make sure not to update `scp` when prompted here, and keep the version in PR50.

Then run the following commands to download the data from [Leduc et
al. (2022)](http://dx.doi.org/10.1101/2021.04.24.441211) and [Woo et
al. (2022)](http://dx.doi.org/10.1016/j.cels.2022.02.003).


```r
library("scpdata")
leduc2022_pSCoPE()
woo2022_macrophage()
```

(We will only run one of these data. The last one is the
shortest/simplest to analyse (possibly a good pick given the time
available), while the first one is more complete and biologically more
interesing.)

Those familiar with Docker can also make use of [Docker containers for
Bioconductor](https://bioconductor.org/help/docker/).

## Workshop material

The workshop will be divided into two parts:

### The infrastructure

The [QFeatures](https://rformassspectrometry.github.io/QFeatures/)
data structure for (bulk and single-cell) quantitative proteomics
and the [scp](https://github.com/UCLouvain-CBIO/scp/) package.

The `QFeature` infrastructure is used to handle data:
- [Intro slides](http://bit.ly/qfeatures_intro)
- [Vignette](https://uclouvain-cbio.github.io/scp/articles/QFeatures_nutshell.html)

Loading SCP data
- [Intro slides](https://uclouvain-cbio.github.io/scp-teaching/read_scp_data#1)
- [Vignette](https://uclouvain-cbio.github.io/scp/articles/read_scp.html)

### Modelling

We will apply the *scplainer* modelling approach, described in
[Modelling single-cell proteomics data with linear
models](https://www.biorxiv.org/content/10.1101/2023.12.14.571792v2).

The
[SCP.replication](https://uclouvain-cbio.github.io/SCP.replication/index.html)
repository provides replication/analysis workflow for several datasets
that can be directly accessed in
[scpdata](https://bioconductor.org/packages/release/data/experiment/html/scpdata.html). We
will be practicing one of the *scplainer* analyses.
