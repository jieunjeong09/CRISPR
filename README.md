# CRISPR screen processing in R

CRISPR screens have proven valuable for identifying therapeutic targets in cancers, which can vary among different types and subtypes. Genes that exhibit amplification may serve as potential tumor suppressors that retain their function in cancer, but their effectiveness is hindered by the activity of other genes. Thus, these genes present indirect targets.

Conversely, genes that show a decline in cell counts after knockout relative to controls represent potential direct targets, as their disruption impairs cancer growth. This group may include genes that interact with the indirect targets described above.

CRISPR screens can also be applied to other areas of investigation beyond neoplasms, although the interpretation of fold changes will depend on the specific biological context. In any setting, further omics analyses—linking the results with transcriptomics, gene sets, and biological pathways—may be necessary to fully interpret the screening data.

Here, I developed and tested Files_to_DF, my workflow for constructing the data frame (or table) that serves as the input for the existing CRISPRcleanR workflow, ccr.AnalysisPipeline. The latter can be executed with a single function call to run the entire pipeline. In fact, any collection of FASTQ files can be processed with this script.

The count table can help reveal if a dataset is unreliable. For example, if the total number of counts in the samples is below 6 million, the CRISPRclean workflow will not operate with the default parameters, and if these totals are much lower, the data are likely unreliable. Additionally, other tests on mapping results can uncover anomalies.
