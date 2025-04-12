# CRISPR screen processing in R


CRISPR screens proved to be valuable in identifying therapeutic targets
in cancers that may differ in different types and subtypes.  Genes that
show amplification are potential tumor suppresing genes that retained
their function in cancer but are hindered by activity of other genes
so are not sufficiently effective.  Thus they present indirect 
targets.

Genes that show decline in cell counts after knockout relative to Control 
represent potential direct targets as they promote cancer growth,
including genes interating with indirect targets describe above.

CRISPR screens may be applied in other investigations, not involving
neoplasm, but interpretation of fold changes would depend on biological
context.  But whatever the context, further omics analysis, connecting
the results with transcriptome, gene sets and biological pathways
may be needed to interpret screen results.

Here I developed and tested Files_to_DF, my workflow for constructing 
the data frame (or table) that can be the input for the existing 
CRISPRcleanR workflow, ccr.AnalysisPipeline,
the latter can be used with a single function call to a function
that runs this pipeline.  Actually, any collection of fastaq files
can be processed with this script, but for the 

The count table can reveal if the data set is unreliable, first, if
thes sum of counts in samples is below 6 million, CRISPRclean
workflow will not work with default parameters, and if those sums
are much lower, data is unreliable.  There are also other tests
on mapping results that can reveal anomalies.


