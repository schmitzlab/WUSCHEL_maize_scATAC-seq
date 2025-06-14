# Overview of this repo
The scrtips are for the [manuscript](https://www.biorxiv.org/content/10.1101/2024.05.13.593957v1) entitled "WUSCHEL-dependent chromatin regulation in maize inflorescence development at single-cell resolution".
They can be used for more than two genotype comparisions in scATAC-seq data.

# Repository Structure 
## submission_scripts
`submission_scripts` directory includes SLURM submission scripts for running the pipeline steps on a compute cluster. Each script wraps a specific component in handling resource allocation, environment setup, and job execution.
They are organized numerically to reflect the order of execution.
  
## workflow_scripts
`workflow_scripts` directory contains core R, Python, and shell scripts that perform specific analyses in a modular and reusable fashion. Each subdirectory represents a distinct step or module of the analysis pipeline.

* `Alignment/`: Scripts for aligning raw reads using Cell Ranger ATAC, and summarizing mapping results.
* `Annotation_Cluster/`: Scripts for annotating clusters, generating UMAP visualizations, and identifying marker genes.
* `Clustering/`: R scripts to perform clustering, UMAP projection, and comparisons across replicates.
* `Correlation/`: Scripts to calculate correlation matrices across replicates, gene bodies, and peak-level accessibility.
* `dACR/`: Main scripts for identifying and analyzing differentially accessible chromatin regions (dACRs).
* `dACRAdditionalAnalysis/`: Downstream analysis of dACRs, including gene association, heatmaps, and statistical summarization.
* `FindCommonACRPos_with500pbLength/`:  Scripts for identifying reproducible ACR positions and processing them to standardized lengths.
* `Mapping_RefiningBam/`: Shell scripts to refine BAM files via deduplication and removal of multimapped reads.
Meme/: Scripts to discover and analyze motifs in ACRs using MEME suite tools.
* `MotifDeviation/`: R scripts to compute motif accessibility deviations using ChromVAR.
* `PeakCalling_byCellTypes/`: Scripts for cell-type-specific peak calling, merging, and classification of ACRs.
* `SocratesStart_QC/`: Scripts to initialize Socrates objects, filter cells, and assess quality control metrics.
* `Viualization/`: R scripts to generate summary figures including dot plots, density plots, pie charts, and heatmaps.

## functions
`functions` directory contains standalone R functions that are sourced by other scripts. 

## Revision_GenomeBiology
`Revision_GenomeBiology` directory contains the additional analysis & visualization scripts. They were added during revision in genome biology journal.
The scripts are written in Rmd to make it easy to check figures and scripts together.

