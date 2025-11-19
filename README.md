# Read-Alignment-Burrows-Wheeler-Transform-BWT-
Read Alignment &amp; Burrows–Wheeler Transform (BWT)
# 🧬 Genomic Read Alignment Toolkit: BWA and Bowtie2 Workflows

This repository contains a set of **Jupyter Notebooks** that implement standardized bioinformatics pipelines for **short read alignment** using two industry-standard tools: **BWA (Burrows-Wheeler Aligner)** and **Bowtie2**.

Each notebook focuses on aligning sequencing reads to a specific chromosome from the **Human Reference Genome (hg38)**, demonstrating essential steps from data retrieval to final alignment metrics. This structure is ideal for learning, benchmarking, and quality control (QC) testing on large-scale genomic data.

## 🚀 Key Features

* **Dual Aligner Demonstration:** Compares the performance and output of **BWA-MEM** and **Bowtie2** within the same environment.
* **Comprehensive Workflow:** Covers all steps required for alignment:
    1.  **Data Retrieval:** Downloads FASTQ reads from the **SRA database** (using a common accession for testing).
    2.  **Reference Preparation:** Downloads the FASTA file for a specific human chromosome (hg38).
    3.  **Indexing:** Creates the necessary reference indices for both BWA and Bowtie2.
    4.  **Alignment:** Executes both BWA-MEM and Bowtie2 alignment commands.
    5.  **QC & Conversion:** Sorts, converts (SAM to BAM), and indexes the final alignment files (`.bam`, `.bai`).
* **Modular Design:** The pipelines are modular, easily allowing users to substitute the reference chromosome, accession ID, or alignment parameters for customized projects.
* **Specific Chromosome Analysis:** Includes dedicated notebooks for Chromosomes 20, 21, 22, and Y.

---

## 📁 Repository Structure

Each notebook follows an identical workflow structure but targets different reference chromosomes:

| Notebook File | Targeted Reference | Primary Use Case |
| :--- | :--- | :--- |
| `*_on_hg38_chr20_.ipynb` | **Human Chromosome 20** | Basic alignment and tool comparison. |
| `*_on_hg38_chr21_.ipynb` | **Human Chromosome 21** | Alignment demonstration (e.g., for Down Syndrome studies). |
| `*_on_hg38_full_chr20__.ipynb` | **Human Chromosome 20** | (Replication or extended demonstration). |
| `*_on_hg38_full_chrY__.ipynb` | **Human Chromosome Y** | Sex-specific alignment demonstration. |
| `*_on_hg38_chr22.ipynb` | **Human Chromosome 22** | Alignment demonstration. |

---

## 🛠️ Prerequisites and Execution

### Requirements

To run these notebooks, you need a Python environment (like Google Colab or JupyterLab) with access to a Linux terminal and the following tools (which the script installs):

* **`sra-toolkit`** (for `fastq-dump` or `prefetch`)
* **`BWA`** (Burrows-Wheeler Aligner)
* **`Bowtie2`**
* **`samtools`** (for file manipulation and indexing)

### How to Run

1.  Open the desired notebook file (e.g., `Read_Alignment_with_BWA_and_Bowtie2_tools_on_hg38_chr22.ipynb`) in Google Colab or a Jupyter environment.
2.  Execute all cells sequentially. The initial cells will handle environment setup, tool installation, and data download.

---

## 📂 Key Output Files

Each alignment run generates the following standard files in the working directory:

| Filename Prefix | Format | Tool | Description |
| :--- | :--- | :--- | :--- |
| `*_BWA_Aligned.sam` | SAM | BWA | Uncompressed text file containing the sequence alignment map. |
| `*_BWA_Aligned.bam` | BAM | BWA | Compressed binary alignment file (final output). |
| `*_Bowtie2_Aligned.sam` | SAM | Bowtie2 | Uncompressed text file containing the sequence alignment map. |
| `*_Bowtie2_Aligned.bam` | BAM | Bowtie2 | Compressed binary alignment file (final output). |
| `*_Aligned.bam.bai` | BAI | samtools | **Index file** required for viewing BAM files in genome browsers (like IGV). |
