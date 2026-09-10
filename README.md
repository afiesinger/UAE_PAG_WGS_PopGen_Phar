# Persistence of the coral *Porites harrisoni* in the Persian/Arabian Gulf is underpinned by strong selection on few genomic loci

![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20732674.svg)

This repository contains all code to generate the data and figures presented in the following manuscript: tbd (submitted to Nat Comms, June 2026)

## Prerequisites

- shell/bash command line
- conda / mamba for environment management
- R / RStudio

## Software & Data Availability

### 1. UAE_PAG_WGS_PopGen_Phar/preprocessing

Raw whole genome sequencing data:
> NCBI BioProject [PRJNA1191362](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1191362) nested under the Umbrella Project [PRJNA749006](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA749006)

<img src="https://skillicons.dev/icons?i=bash" height="28"/>

- FastQC v0.12.1 (Andrews, 2010)
- BBDuk from the BBMap v39.08 package
- BWA MEM v0.7.18
- SAMtools v1.21
- PICARD v3.1.1
- Sambamba markdup v1.0.1
- GATK HaplotypeCaller, CombineGVCFs, GenotypeGVCFs, SelectVariants, VariantFiltration
- VCFtools v0.1.16

VCF files generated from raw sequencing data can be accessed at the Zenodo repository: 
> Fiesinger, A. & Voolstra, C.R. (2025) “Signatures of host genomic and algal symbiont selection in the coral *Porites harrisoni* from the Persian/Arabian Gulf.” *Zenodo*. ![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17827487.svg)

### 2. UAE_PAG_WGS_PopGen_Phar/popgen

<img src="https://skillicons.dev/icons?i=bash" height="28"/>

- KING v2.2.7
- PLINK v1.90
- ADMIXTURE
- CLUMPP
- VCFtools v0.1.16
- Stairway Plot v2
- ANGSD v0.94

<img src="https://skillicons.dev/icons?i=r" height="28"/>

- pophelper v2.3.1
- ggplot2 v3.4.2

### 3. UAE_PAG_WGS_PopGen_Phar/host_symbiont

ITS2 raw sequencing data: 
> NCBI BioProject [PRJNA1188806](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1188806) nested under the Umbrella Project [PRJNA749006](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA749006)

ITS2 SymPortal run (including all files to download): 
> accessible here on [SymPortal](https://symportal.org/data_explorer/?Study=202307_afiesinger_UAE_GS)

<img src="https://skillicons.dev/icons?i=bash" height="28"/>

- PLINK v1.90

<img src="https://skillicons.dev/icons?i=r" height="28"/>

- stats v4.1.3
- vcfR v1.15.0
- vegan v2.7.2

### 4. UAE_PAG_WGS_PopGen_Phar/sweeps

<img src="https://skillicons.dev/icons?i=bash" height="28"/>

- VCFtools v0.1.16
- Beagle v5.5
- selscan v2.1
- SnpEff v5.3
- SnpSift v5.3
- PopLDDecay v3.40
- pixy 2.0.0
