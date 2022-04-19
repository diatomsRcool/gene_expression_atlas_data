# Gene Expression Atlas Data
Repository for data downloaded from the EBI Gene Expression Atlas and transformed for use in KG-Hub.

All data files are transformed downloads from ebi.ac.uk/gxa/home

Data are downloaded by experiment. Only differential gene expression between treatment and control are considered. Genes with expression between 1 and -1 log2-fold change are deleted. Genes with differential expression adjusted p values less than 0.05 are deleted.

Additional information, such as cultivar, organism part, developmental stage, etc. are gathered from the experimental design metadata at the Gene Expression Atlas website.

Gene identifiers for Arabidopsis are normalized to "AT" locus ids. Environmental stressors, organism parts, and developmental stages are annotated with ontology terms from PECO and PO.

Cultivar, genotype, and ecotype identifiers are manually normalized as needed.

# Data File Description
cold_heat_gene_expression.txt: Differential gene expression from experiments with cold and heat stress in A. thaliana, O. sativa, P. trichocarpa, and Z. mays.

drought_salt_gene_expression.txt: Differential gene expression from experiments with drought and salt stress in A. thaliana, O. sativa, P. trichocarpa, and S. bicolor

Files are tab delimited and have 14 columns

Gene: Gene identifier. 

Species: Taxonomic binomial of the species being tested

Experiment accession: Persistent, unique identifier provided by Gene Expression Atlas

Comparison: Free text, brief description of experiment

PECOid: CURIE from PECO describing treatment condition. Annotator provided.

log_2 fold change: Gene expression measure provided by Gene Expression Atlas. Corresponds to the comparison in the "Comparison" column. Positive values are increased expression in treatment compared to control. Negative values are decreased expression compared to control.

Adjusted p-value: Provided by Gene Expression Atlas. A measure of the statistical significance of the differential gene expression value. Not always present.

t-statistic: Provided by Gene Expression Atlas. Not always present.

ROid: Applicable biolink predicate. Either biolink:increases_expression_of or biolink:decreases_expression_of depending on value in "log_2 fold change" column. Annotator provided.

developmental stage: Free text from experimental design metadata in Gene Expression Atlas

POid LifeStage: PO CURIE. Annotator provided. Based on text in Experimental design metadata which is reflected in "developmental stage" column. Not always present

anatomical part: Free text from experimental design metadata in Gene Expression Atlas. The part of the plant where the got the tissue to analyze.

POid Anatomy: PO CURIE. Annotator provided. Based on text in Experimental design metadata which is reflected in "anatomical part" column. Not always present.

cultivar: Free text from Gene Expression Atlas experimental design metadata. Any information about the cultivar, genotype, or ecotype will be here. Not always present.
