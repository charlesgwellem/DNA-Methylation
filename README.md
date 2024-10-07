# DNA Methylation Analysis

## **Overview**

This project explores DNA methylation data to study epigenetic regulation and its relationship with phenotypic variation, particularly focusing on identifying **CpG** islands and assessing methylation differences between normal and cancerous tissue samples.

DNA methylation is a process that regulates gene expression by silencing genes. In this project, **CpGs**—regions where cytosine is followed by guanine—are analyzed, and **CpG islands** (regions with a high concentration of CpGs) are identified. The project involves exploratory analysis of methylation data, particularly from chromosome 22, and investigates differentially methylated regions (DMRs) in colon cancer and normal tissue samples.

## **Project Structure**

### **Sections Covered:**

1. **Exploratory Data Analysis:**
   - Analysis of CpGs on **chromosome 22**, including the calculation of **GC content**, the number of **CpG** and **GpC** occurrences, and an investigation of CpG islands using the **AnnotationHub** Bioconductor package.

2. **CpG Islands Assessment:**
   - Identification and exploration of CpG islands using **BSgenome.Hsapiens.UCSC.hg19** and **AnnotationHub** to retrieve and analyze CpG island annotations.
   - Calculation of the observed-to-expected ratio of CpGs and GpCs and their distributions in CpG islands.

3. **Analysis of Colon Cancer Methylation Data:**
   - Comparison of **normal** and **cancer** tissue samples using data from the **Illumina 450K array**.
   - Visualization of methylation measurements with density plots to observe the differences between normal and cancer samples.

4. **Statistical Testing for Differential Methylation:**
   - A **limma** package is used to identify differentially methylated CpGs between normal and cancerous tissues.
   - A **volcano plot** is used to reveal differences, and regions with the most significant methylation differences are explored.

5. **Bumphunter Analysis:**
   - Use of the **bumphunter** package to identify contiguous differentially methylated regions (DMRs) across the genome, focusing on cancer vs. normal tissue.

6. **Smoothing and Visualization of Methylation Differences:**
   - Application of **Loess smoothing** to visualize the methylation differences across genomic regions.

## **Installation**

### **Dependencies**
This analysis requires the following R packages:

- `BSgenome.Hsapiens.UCSC.hg19`
- `AnnotationHub`
- `coloncancermeth`
- `limma`
- `rafalib`
- `bumphunter`

You can install these packages using:
```r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("BSgenome.Hsapiens.UCSC.hg19", "AnnotationHub", "coloncancermeth", "limma", "rafalib", "bumphunter"))
```

## **Usage**

To run the analysis:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/dna_methylation_analysis.git
   cd dna_methylation_analysis
   ```

2. **Run the RMarkdown script**:  
   Open the `dna_methylation.Rmd` file in RStudio and knit the document to generate the HTML or PDF report.

3. **Explore results**:  
   The results of the CpG island analysis, differential methylation testing, and region analysis will be displayed in the output.

## **Key Results**

### **Exploratory Data Analysis of CpGs:**
- **GC Content**: The GC content for a selected region on **chromosome 22** is calculated to be 58.3%.
- **CpGs and GpCs**: The analysis reveals the occurrence of 10 **CpGs** and 65 **GpCs** in a 1000 base pair region on **chromosome 22**.

### **Differential Methylation in Cancer vs. Normal Tissue:**
- **Density Plot**: A bimodal distribution of methylation values, showing lower peaks for cancer samples, indicates differential methylation.
- **Volcano Plot**: Highlights differentially methylated regions (DMRs) with significant effect sizes between normal and cancer samples.
  
### **Bumphunter Results:**
- The **bumphunter** analysis identifies contiguous regions with significant methylation differences across cancerous and normal tissues.
- **Loess Smoothing**: Applied to visualize the trend of methylation differences in specific regions.

## **Conclusions**

This project demonstrates how **DNA methylation analysis** can be applied to identify significant **CpG islands** and **differentially methylated regions** (DMRs) that distinguish between normal and cancerous tissue. The use of **Bumphunter** and **Loess smoothing** highlights significant regions that could be explored further for potential biomarker identification.

## **Session Info**
To view the R session information and packages used, run:
```r
sessionInfo()
```
