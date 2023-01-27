# Bioinformatic_Tutorials


| **Online Training Tools**                                               |
|-------------------------------------------------------------------------|
|                                                                         |
| **Online Training from Cambridge University**                           |
|                                                                         |
| https://www.cruk.cam.ac.uk/core-facilities/bioinformatics-core/training |
|                                                                         |
| **Extra Training from Cambridge**                                       |
| http://bioinformatics-core-shared-training.github.io/                   |
|                                                                         |
| **Python Tutorial Website**                                             |
| https://thomas-cokelaer.info/tutorials/python/index.html                |
|                                                                         |
| **Coding Tutorial**                                                     |
| https://www.w3schools.com/                                              |



# Thing's I am asked about repetatively...

### Questions:
1. Difference between p-value and FDR? [Answer1](#fdr)
2. What is batch correction? [Anwer2](#batch-correction)
3. How do you normalize the data? [Answer3](#normalize-data)
4. What is a PCA plot and what does it show us? [Answer4](#pca)
5. What statistical test should I run? Parametric vs non-parametric... [Answer5](#parametric-vs-nonparametric)
6. What is RNA-seq? [Answer6](#rna-seq)
7. What is CHiP-seq? [Answer7](#chip-seq)
8. What is SLAM-seq? [Answer8](#slam-seq)
9. What is ATAC-seq? [Answer9](#atac-seq)
10. What is CUT&RUN? [Answer10](#cut&run)
11. What is a consensus peak set in Cut and Run? [Answer11](#consensus-peaksets)
12. What is Hi-C? [Answer12](#hi-c)
13. How can machine learning help my lab? [Answer13](#machine-learning)
14. What is Support Vector Machinery (SVM)? [Answer14](#svm)
15. What is the difference between Pearson's and Spearman's correlation? [Answer15](#pearson-and-spearman-correlation)


### Answers:

# FDR 
A p-value is a measure of the evidence against a null hypothesis. It is the probability of observing a test statistic as extreme or more extreme than the one computed from the sample, assuming that the null hypothesis is true. A small p-value (typically less than 0.05) indicates strong evidence against the null hypothesis and in favor of the alternative hypothesis.

The false discovery rate (FDR) is a measure of the proportion of false positives among all the significant results. It is defined as the expected proportion of false positives among all the significant results (i.e., results with a p-value less than a specified threshold). An FDR of 0.05, for example, means that 5% of the significant results are expected to be false positives.

In short, a p-value is a single number calculated for a given test statistic, while FDR is a measure of the overall rate of false positives among multiple tests.


# Batch Correction
Batch correction is a technique used to correct for systematic errors that are introduced during the measurement of biological samples. These errors can be caused by variations in the experimental conditions, such as differences in the individual performing the experiment, specific antibody LOT#s, location of the experiment, or variations in the time of measurement. Batch correction methods aim to remove these errors by normalizing the data to account for these variations, so that the results can be more accurately compared across different batches of samples.

There are several different techniques that can be used for batch correction, depending on the specific data and experimental conditions. Some common techniques include:

- ComBat: This method uses a linear model to adjust for batch effects by fitting a "batch" variable to the data. It then uses this model to estimate the batch effect and adjust the data accordingly.

- SVA: This method uses singular value decomposition (SVD) to identify and remove sources of variation that are likely to be batch effects. It then uses the remaining variation to estimate the batch effect and adjust the data.

- RUV: This method uses a general linear model (GLM) to estimate and remove batch effects by fitting "nuisance" variables that capture sources of variation that are likely to be batch effects.

- RUV-seq: This method is similar to RUV but is specifically designed for RNA-seq data, it uses a negative binomial model to estimate the expression of each gene and then removing the batch effect by fitting the "nuisance" variables.

- normExp: This method uses a quantile normalization to adjust for batch effects.

These are just a few examples of the many batch correction methods that are available. The choice of method will depend on the specific data and experimental conditions, as well as the goals of the analysis. It's important to keep in mind that batch correction is not a one-size-fits-all solution and it's important to validate the results with appropriate biological replicates.


# Normalize Data
Data normalization is the process of transforming the values of a dataset so that it conforms to a specific standard. This is often done to improve the performance of machine learning algorithms and make them less sensitive to the scale of the features. It is also done to make two different objects more comparable by setting them on the same scale.

There are several methods of normalization, including:

- Min-Max Scaling: This method scales the values of a feature to a specific range, usually between 0 and 1. This is done by subtracting the minimum value of the feature from each value and then dividing by the range (i.e., the difference between the maximum and minimum values).

- Z-score Normalization: This method scales the values of a feature by subtracting the mean of the feature from each value and then dividing by the standard deviation. This results in a feature with a mean of 0 and a standard deviation of 1.

- L2 Normalization: This method scales the values of a feature by dividing each value by the L2 norm of the feature. This ensures that each feature has a magnitude of 1.

- Decimal Scaling: This method scales the values of a feature by moving the decimal point a certain number of places to the left or right.

- Logarithmic Scaling: This method scales the values of a feature by applying a logarithm transformation to them.

It's important to note that the choice of normalization method depends on the specific characteristics of the dataset and the algorithm you're using. And it's good practice to do some experiment with different method and choose the one that works best.


# PCA
Principal component analysis is a data reduction technique used to describe the variance between samples. Most often, the top two principal components (the two that expain the majority of the variance of the dataset) are plotted against each other. Once you label the samples by experimental condition you can start to determine what factors are contributing most to the differences we see in the data.

PCA allows us to identify patterns in data based on the correlation between features, and express the dataset with a new set of uncorrelated variables, called principal components which are a linear combination of the original features and are ranked by the amount of variance they explain.

# Parametric vs Nonparametric
Parametric tests and nonparametric tests are two types of statistical tests used to compare groups or make inferences about a population.

Parametric tests make assumptions about the underlying probability distribution of the data, typically that the data is normally distributed. Examples of parametric tests include t-tests, ANOVA, and linear regression. These tests require relatively large sample sizes and the assumptions of normality must be met for the tests to be considered valid.

Nonparametric tests do not make assumptions about the underlying probability distribution of the data and are more robust to violations of assumptions. Examples of nonparametric tests include the Wilcoxon rank-sum test, the Kruskal-Wallis test, and the chi-squared test. These tests are often used when the sample size is small or when the assumptions of normality are not met.

In general, nonparametric tests are less powerful than parametric tests but are more robust to violations of assumptions. However, nonparametric tests can be less efficient and may have a higher type II error rate.

It is important to note that when the assumptions of parametric tests are met, they tend to be more powerful and efficient than nonparametric tests. But when assumptions are not met, nonparametric tests are a safer choice.


# RNA-Seq
RNA-seq (RNA sequencing) is a technique that allows for the comprehensive and quantitative analysis of the RNA content of a cell or tissue sample. It involves sequencing the RNA molecules in a sample by breaking them down into smaller fragments, and then determining the order of the nucleotides (A, C, G, and U) in each fragment.

The process starts with extracting the RNA from the sample, then the RNA is converted into cDNA (complementary DNA) using reverse transcriptase. The cDNA is then fragmented and the ends are ligated with adapters. The fragmented cDNA is then subject to high-throughput sequencing (such as Illumina) and the generated sequences are aligned to a reference genome.

RNA-seq can be used to measure the expression levels of all genes in a sample, identify novel transcripts, detect fusion genes, and quantify the abundance of different isoforms of a gene. It has wide applications in functional genomics, transcriptomics, biomarker discovery and more.


# CHiP-Seq
ChIP-seq (chromatin immunoprecipitation sequencing) is a technique used to identify the locations of a specific protein (or histone modification) on a genome. The technique involves cross-linking the protein of interest to its associated DNA, fragmenting the DNA, and then using an antibody specific to the protein of interest to pull down the protein-DNA complexes. The pulled-down DNA is then sequenced to determine the location of the protein on the genome.

The process starts with treating cells with a chemical cross-linker, which fixes the protein of interest to its associated DNA. The chromatin is then fragmented and the protein of interest is pulled down by an antibody. The pulled-down DNA is then subject to high-throughput sequencing (such as Illumina) and the generated sequences are aligned to a reference genome.

ChIP-seq is a powerful tool for studying the genome-wide distribution of various proteins and histone modifications, and the regulation of gene expression. It is widely used in the field of epigenetics, to study the function of proteins involved in chromatin remodeling, and to identify transcription factor binding sites.

# SLAM-seq
SLAM-seq (Stimulator of Interferon Genes-seq) is a technique that allows for the identification of active enhancers in a cell. SLAM-seq is based on the activation of the Stimulator of Interferon Genes (STING) pathway, which leads to the recruitment of a protein called cGAS to the enhancer regions. cGAS in turn catalyzes the production of a second messenger called cGAMP, which can be detected by a specific antibody.

The process starts by treating the cells with a chemical stimulator which activates the STING pathway. Then, the cGAMP is pulled down by an antibody and the pulled-down DNA is then subject to high-throughput sequencing (such as Illumina) and the generated sequences are aligned to a reference genome.

SLAM-seq is a powerful tool for identifying enhancer regions in the genome and understanding the regulation of gene expression. It is particularly useful in the study of developmental biology, cancer research and immune response, as enhancer regions play an important role in these processes.


# ATAC-seq
ATAC-seq (Assay for Transposase-Accessible Chromatin using high-throughput sequencing) is a technique used to study the open chromatin regions in a genome. It is based on the action of the transposase enzyme which is able to access and cleave nucleosomal DNA at specific regions, those regions are regions that are accessible to the regulatory elements such as transcription factors, and therefore are important for gene expression.

In the ATAC-seq protocol, the transposase enzyme is used to cut the DNA at accessible regions and the resulting DNA fragments are then captured and sequenced. The resulting data can be used to identify regions of open chromatin and can be used to understand the regulation of gene expression and the organization of the genome.

ATAC-seq is a powerful technique for identifying regions of open chromatin and can be used to study a wide range of biological processes, including development, disease, and response to environmental changes.


# CUT&RUN
Cut and Run (Cleavage Under Targets and Releasing Nucleases) is a technique used to identify the location of specific proteins on a genome. It is a variation of the ChIP-seq technique, but it uses a different approach for fragmenting the DNA.

Instead of cross-linking the protein of interest to its associated DNA, Cut and Run uses a nuclease, such as micrococcal nuclease (MNase), to cleave the DNA at specific locations. MNase preferentially cleaves at regions of DNA that are not bound by proteins or in regions with a low level of chromatin compaction. Then, the protein of interest is pulled down by an antibody and the pulled-down DNA is then subject to high-throughput sequencing (such as Illumina) and the generated sequences are aligned to a reference genome.

Cut and Run is a powerful tool for identifying the location of specific proteins on the genome and for understanding the regulation of gene expression. It can be used to study the function of different chromatin-associated proteins, such as transcription factors, co-activators, and co-repressors. This technique has been applied to various organisms, from yeast to human, and in different cellular contexts, such as stem cells and cancer cells.


# Consensus Peaksets
A consensus peak in Cut and Run is a peak that appears in multiple samples or replicates of the same experimental condition. It is considered a reliable indicator of a specific binding site for the protein of interest, as it is likely to be a true positive binding event. Consensus peaks can be identified using bioinformatics tools such as MACS2.


# Hi-C
Hi-C is a technique used to study the three-dimensional organization of chromosomes within a cell's nucleus. It is used to map the interactions between different regions of the genome, and can help scientists understand how genes are regulated and how genetic information is passed from one generation to the next. The technique involves crosslinking DNA with a chemical reagent, cutting it with restriction enzymes, and then using high-throughput sequencing to detect the interactions between different regions of the genome. Hi-C data can be used to construct 3D models of chromosomes, which can help researchers better understand the role of chromatin structure in gene regulation and other processes.


# Machine Learning
Machine learning (ML) can help biology labs in a variety of ways. Some examples include:

- Data analysis: ML algorithms can be used to analyze large and complex data sets generated by high-throughput experiments, such as RNA-seq, ChIP-seq, and SLAM-seq. These algorithms can be used to identify patterns and relationships in the data that would be difficult or impossible to detect by manual inspection.

- Image analysis: ML algorithms can be used to analyze images, such as microscopy images, to identify and quantify features of interest, such as cells or organelles. This can help to automate and speed up image analysis, and reduce the need for manual annotation.

- Drug discovery: ML algorithms can be used to analyze large data sets of chemical compounds and predict which compounds are likely to be effective drugs. This can help to speed up the drug discovery process and identify new drug candidates.

- Predictive modeling: Machine learning can help researchers to predict the outcome of experiments before they are performed, based on the data that they already have. This can help researchers to optimize their experiments and avoid wasting time and resources on experiments that are unlikely to be successful.

- Automation: Some machine learning algorithms can help automate repetitive and time-consuming tasks in the lab, such as data entry, data cleaning, and data analysis.

Overall, machine learning can help biology labs to make sense of large and complex data sets, and to identify new insights and opportunities for research.


# SVM
Support Vector Machine (SVM) is a type of supervised learning algorithm that can be used for classification and regression tasks. The goal of an SVM is to find a hyperplane (a line or a plane) that best separates the data into different classes. In a two-class problem, the hyperplane is chosen so that it maximizes the margin, which is the distance between the hyperplane and the closest data points from each class, known as support vectors. This approach allows SVM to handle non-linearly separable data by transforming it into a higher-dimensional space where a linear boundary can be found. SVM can also be used for multi-class problems by training multiple binary classifiers.


# Pearson and Spearman Correlation
- Pearson correlation: Pearson correlation evaluates the linear relationship between two continuous variables. 
- Spearman correlation: Spearman correlation evaluates the monotonic relationship. The Spearman correlation coefficient is based on the ranked values for each variable rather than the raw data. 
