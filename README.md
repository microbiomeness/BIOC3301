# BIOC3301
Folder shows all code used on QIIME 1.9.1 in the metagenomic processing of 16S rRNA gene V4 region to determine the pH dependency of Sphingobacteriales. A mapping file with all metadata and coordinates of the 30 soil samples collected within the Greater London region is also provided under the name map_complete_ph.txt.

Processing workflow is:
* joinends2018.txt 
  * join forward and backward read from sequencing.
* split_libraries2018.txt 
  * demultiplex the sequences with the given barcodes. 
  * Quality score cutoff of greater than or equal to 30 was used to filter the sequences.
* open_ref_OTUs_SILVA128_2018.txt + open_ref_otu_parameters.txt 
  * open reference operational taxonomic unit picking from SILVA128 database to assign OTUs to the sequences. 
  * Matching to reverse strand allowed. 
  * OTU table generated. 
  * Summary of OTU table used to determine lowest sampling depth that is more than 100 sequences (as suggested by Kuczynski et al 2010) for further analyses.
* cda_analyses2018.txt + cda_parameter.txt 
  * core diversity analysis including a-diversity and B-diversity analyses of all OTUs categorised by metadata (SamplePh, SamplePotassium, SamplePhosphorus, SampleNitrogen). 
* OTU table sphingobacteriales.txt 
  * filter original OTU table to only contain Sphingobacteriales. 
* beta_diversity_sphingobacteriales.txt 
  * using the Sphingobacteriales OTU table run B-diversity to find clustering based on abundance of Sphinogbacteriales dependent on pH.
* 2D_PCoA_plots_sphingo.txt 
  * Convert 3D PCoA plot generated by B-diversity analysis into 2D to understand the clustering.
* cluster_quality_sphingo.txt 
  * analyse the quality of the clustering based on pH in the PCoA plots.
* group_significance.txt 
  * analysis of the significance of pH in contributing to the variance in abundance of Sphingobacteriales through the Kruskal-Wallis test. Null hypothesis = All population medians are equal.
* kendall_ph_correlation.txt 
  * nonparametric kendall correlation (looks at rank correlation without assuming any distribution) between pH and abundance of Sphingobacteriales.
