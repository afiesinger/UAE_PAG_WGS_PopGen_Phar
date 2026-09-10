# Persistence of the coral *Porites harrisoni* in the Persian/Arabian Gulf is underpinned by strong selection on few genomic loci

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20732674.svg)]
(https://doi.org/10.5281/zenodo.20732674)

This repository contains all code to generate the data and figures presented in the following manuscript: tbd (submitted to Nat Comms, June 2026)

## Prerequisites

- shell/bash command line
- conda / mamba for environment management
- R / RStudio

## Software & Data Availability

### UAE_PAG_WGS_PopGen_Phar/preprocessing

Raw whole genome sequencing data are available under the NCBI BioProject [PRJNA1191362](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1191362) nested under the Umbrella Project [PRJNA749006](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA749006)

<img src="https://skillicons.dev/icons?i=bash" height="28"/>

- FastQC v0.12.1 (Andrews, 2010)
- BBDuk from the BBMap v39.08 package
- BWA MEM v0.7.18
- SAMtools v1.21
- PICARD v3.1.1
- Sambamba markdup v1.0.1
- GATK HaplotypeCaller, CombineGVCFs, GenotypeGVCFs, SelectVariants, VariantFiltration
- VCFtools v0.1.16

VCF files generated from raw sequencing data can be accessed at the Zenodo repository 
> Fiesinger, A. & Voolstra, C.R. (2025) “Signatures of host genomic and algal symbiont selection in the coral *Porites harrisoni* from the Persian/Arabian Gulf.” *Zenodo*. https://doi.org/10.5281/ZENODO.17827487.

### UAE_PAG_WGS_PopGen_Phar/popgen

- KING v2.2.7
- PLINK v1.90
- ADMIXTURE
- CLUMPP
- VCFtools v0.1.16
- Stairway Plot v2
- ANGSD v0.94

<img src="https://skillicons.dev/icons?i=r" height="32"/>

- pophelper v2.3.1
- ggplot2 v3.4.2

### UAE_PAG_WGS_PopGen_Phar/host_symbiont

ITS2 raw sequencing data are available under the NCBI BioProject [PRJNA1188806](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1188806)

The ITS2 SymPortal run is accessible on [SymPortal](https://symportal.org/data_explorer/?Study=202307_afiesinger_UAE_GS)

<img src="https://skillicons.dev/icons?i=bash" height="32"/>

- PLINK v1.90

<img src="https://skillicons.dev/icons?i=r" height="32"/>

- stats v4.1.3
- vcfR v1.15.0
- vegan v2.7.2

### UAE_PAG_WGS_PopGen_Phar/sweeps

We searched for signatures of selection utilizing genetic differentiation and haplotype homozygosity measures using the filtered VCF file for selective sweep analyses (see above). To quantify genomic divergence between the PAG (sites SA and SY) and GO (site AA) populations of Porites harrisoni, we computed pairwise Weir and Cockerham’s FST along the genome with VCFtools v0.1.16. To calculate haplotype homozygosity statistics, genotypes were first phased and imputed in Beagle v5.5 (Browning et al., 2018, 2021). Then, cross-population extended haplotype homozygosity (XP-EHH) (Sabeti et al., 2007), integrated haplotype score (iHS) (Voight et al., 2006), number of segregating sites by length (nSL) (Ferrer-Admetlla et al., 2014), and integrated haplotype homozygosity pooled (iHH12) (Torres et al., 2018) were calculated using selscan v2.1 (Szpiech, 2025; Szpiech & Hernandez, 2014) and normalized to account for genome-wide differences in haplotype length between the PAG and GO populations using the selscan normalization script (Szpiech, 2025). SNPs were considered outliers (i.e., in candidate regions of selection) if two conditions were met: (i) they were in the top 0.1% quantile of FST values and (ii) the absolute XP-EHH score was in the top 1% tail of the statistic (corresponding to an absolute XP-EHH ≥ 3.09) and positive, reflecting the presence of extended haplotypes (indicative of selective sweeps) in the PAG populations compared to the GO. Candidate loci identified through both the FST and XP-EHH outlier analysis, were analyzed with SnpEff v5.3 (Cingolani et al., 2012) to annotate and predict the effects of genetic variants (e.g., amino acid change in the coding sequence of a gene) based on the P. harrisoni reference genome, and the results were filtered using SnpSift v5.3 (Cingolani et al., 2012). For each identified candidate region, allele frequency was calculated with VCFtools v0.1.16 and plotted in R to determine whether alleles in the respective regions were at or near fixation in the PAG corals. Further, linkage disequilibrium decay was assessed using PopLDDecay v3.40 (Zhang et al., 2019) on the population structure VCF file before LD pruning (--minQ 30, --maf 0.05, --max-missing 0.8, --hwe 0.001, --min-alleles 2, --max-alleles 2). Lastly, to identify regions where loss in nucleotide diversity (π) could be observed in one population but not the other (indicative of directional selection), π was calculated on the VCF file output by GATK with an additional flag to include all variant sites (--include-non-variant-sites). Clone mates were removed as above, and π was calculated with pixy (Korunes & Samuk, 2021). 




