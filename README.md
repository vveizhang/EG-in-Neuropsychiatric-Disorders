# Essential Genes from Genome-wide Screening as a Resource for Neurological and Mental Disorders Gene Discovery








#### Background
Genome-wide screenings of ‘essential genes’, i.e., genes required for an organism or cell survival, have been traditionally conducted in vitro in cancer cell lines, limiting the translation of results to other tissues and non-cancerous cells. Recently, an in vivo screening was conducted in adult mouse striatum tissue, providing the first genome-wide dataset of essential genes in neuronal cells.
![2GeneList](./Files/2GeneList.png)

Here, we aim to investigate the role of essential genes in brain development and disease risk with a comprehensive set of bioinformatics tools, including integration with transcriptomic data from developing human brain, publicly-available data from genome-wide association studies, de novo mutation datasets for different neuropsychiatric disorders, and case-control transcriptomic data from postmortem brain tissues.


#### Gene ontology (GO) analysis
![Figure 1](./Files/Fig1.jpg)
The above figure shows the Gene ontology (GO) analysis of essential genes. (a) Venn diagram shows overlapping of Neuronal Essential Genes (NEGs) and Achilles Project-specific essential genes (ACEGs). (b) Top biological process GO terms enriched in NEGs and ACEGs. (c) Top cellular component GO terms enriched in NEGs and ACEGs.

We will focus on the specific genes from two studies other than the overlapping of the two gene list, we will refer the genes from in vivo CNS screening as NEGs(Neuronal essential genes), the common essential genes from Project Achilles as ACEGs(Achilles Project-specific essential genes)

####  NEGs are more likely to exhibit differential expression in brain tissue in case-control studies of neuropsychiatric disorders compared to ACEGs

We found 6 datasets in the GEO database with RNA-seq in results from brain tissue of NDD, neurodevelopmental, and psychiatric disorder patients and healthy controls, including AD, ALS, ASD, HD, and SCZ. We initially downloaded the raw gene expression data and then use standard RNA-seq analysis pipeline to get the expression data, then we used the R package DESeq2 to normalize them, followed by a comparison of the DESeq2 p-values (P-DE) of the NEGs and ACEGs.


![Figure 2](./Files/Fig2.jpg)

The above figure shows the NEGs are more likely to exhibit differential expression in brain tissue in neuropsychiatric disorders compared to ACEGs.



#### NEGs and ACEGs are enriched in different co-expression networks and show different temporal expression patterns

We download the Brainspan Developmental Transcriptome data: which covered full period of brain development and all available brain regions (5.7 PCW – 70 years of age; 1,340 samples). We used weighted gene co-expression network analysis (WGCNA) package to construct co-expression modules.

An adjacency matrix was created by computing the correlation between the expression levels of each gene with every other gene using signed biweight correlations; a soft threshold of power of 15 was used to achieve scale free topology.
![Soft Power pick](./Files/SoftPower.png)




The adjacency matrix was transformed into a topological overlap matrix (TOM). The network dendrogram (Figure 2S) was generated from the TOM dissimilarity matrix (1-TOM). The ‘Dynamic Hybrid’ method was employed with standard parameters (i.e. pamStage = TRUE, minimum module size = 30, deepSplit = 2, pamRespectsDendro=FALSE), modules with ME correlations >0.9 were. 22 modules were generated.
![Gene Clustering](./Files/GeneClustering.png)



Next we investigate the enrichment of two gene sets in different modules and the temporal expression pattern.

![Figure 3](./Files/Fig3.jpg)

The above figure shows Neuronal essential genes (NEGs) and Achilles Project-specific essential genes (ACEGs) are enriched in different modules and show different expression patterns. (A) Module enrichment of NEGs and ACEGs. (B) Eigengene expression patterns of modules M12, M20, and M22. (C) Eigengene expression patterns of modules M11, M9, and M19. (D) Eigengene expression patterns of modules M01, M02, and M16.

We collected GWAS data and rare variants data for neuropsychiatric disorders, as well as de novo mutation data from denovo-db23, and then tested the overlap between NEGs and ACEGs among these genetic variants. 
The data is summarized in the following table.


![table](./Files/table.png)



#### Association of NEGs and ACEGs with neuropsychiatric genetic risk.


![Figure 4](./Files/Fig4.jpg)


From the above figure, we found that both NEGs and ACEGs significantly overlap with the NDD and psychiatric disorders risk genes41, such as ASD, ID, EPI, CP and SCZ, while only NEGs are enriched in neurodegenerative disorders (PD and ALS) in de novo mutations.


#### General gene features of NEGs and ACEGs.


![Figure 5](./Files/Fig5.jpg)

Comparation of other features: probability of a gene being intolerant to LoF (pLI), probability of mutation, gene-level integrated metric of negative selection (GIMS) scores, and haploid insufficiency of Neuronal Essential Genes (NEGs) and Achilles Project-specific essential genes (ACEGs). (A) pLI of NEGs and ACEGs. (B) Probability of mutation of NEGs and ACEGs. (C) Haploid insufficiency rate of NEGs and ACEGs. (D) Transcript Length of NEGs and ACEGs. (E) Tissue expression specificities of NEGs and ACEGs.





#### Reference
1. Tsherniak A, Vazquez F, Montgomery PG, et al. Defining a Cancer Dependency Map. (1097-4172 (Electronic)).
2.	Shin JH, Lee Hk Fau - Khang SK, Khang Sk Fau - Kim DW, et al. Neuronal tumors of the central nervous system: radiologic findings and pathologic correlation. (0271-5333 (Print)).
3.	Wertz MH, Mitchem MR, Pineda SS, et al. Genome-wide In Vivo CNS Screening Identifies Genes that Modify CNS Neuronal Survival and mHTT Toxicity. (1097-4199 (Electronic)).
4. Love MI, Huber W, Anders S. Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. Genome Biology. 2014;15(12):550
5. de Leeuw CA, Mooij JM, Heskes T, Posthuma D. MAGMA: generalized gene-set analysis of GWAS data. (1553-7358 (Electronic)).
6. Langfelder P, Horvath S. WGCNA: an R package for weighted correlation network analysis. (1471-2105 (Electronic)).
