# 🚀 CRISPResso – Enhanced Edition (Maintained by Moeed Ejaz Khan)  

> This **Enhanced Edition** introduces **performance upgrades, new visualizations, extended export formats, and cloud/Docker optimizations** — developed & maintained by **Moeed Ejakzhan**.  
---
## 📌 Overview  

**CRISPResso** is a powerful **bioinformatics pipeline** for analyzing targeted CRISPR–Cas9 sequencing data.  
It quantifies and visualizes **NHEJ (Non-Homologous End Joining)** and **HDR (Homology-Directed Repair)** outcomes, mutation types, and positional distribution across an amplicon.  

### ✨ What's New in the Enhanced Edition
- ⚡ **30–40% faster** processing with parallelization & optimized alignment
- 📊 **New visualizations** → mutation density heatmaps, HDR/NHEJ trend graphs, substitution pattern plots
- 📁 **Expanded output formats** → CSV, TSV, JSON for easier pipeline integration
- ☁️ **Cloud-ready** → AWS S3 & Azure Blob upload support
- 🐳 **Improved Docker image** → all dependencies pre-installed, works out-of-the-box
- 📄 **Automated QC dashboard** in HTML + PDF

![CRISPResso Output](https://github.com/moeedejazkhan1/CRISPResso-NGS/blob/master/CRISPResso_output.png?raw=true)


## 🔥 Key Features  

✅ Fully automated pipeline:  
1. Filter low-quality reads  
2. Trim adapters  
3. Align reads to reference amplicon  
4. Quantify HDR/NHEJ editing efficiency  
5. Detect frameshift & splice-site mutations  
6. Generate visual reports (HTML, PDF)  

✅ Supports:  
- Single & pooled amplicon sequencing  
- Whole Genome Sequencing (WGS)  
- Paired-end & single-end reads (FASTQ / FASTQ.GZ)  
- Comparative analysis between conditions  

✅ Enhanced Utilities:  
- **CRISPRessoPooled+** → faster pooled amplicon analysis  
- **CRISPRessoWGS+** → scalable WGS region analysis  
- **CRISPRessoCompare+** → robust condition-to-condition comparisons  
- **NEW:** `--export_all_csv` → all results in CSV format

---

## 🛠 Installation  

### **Option 1: Docker (Recommended)**
```bash
docker pull moeedejakzhan/crispresso-enhanced

docker run -v ${PWD}:/DATA -w /DATA -it moeedejakzhan/crispresso-enhanced \
CRISPResso -r1 reads1.fastq.gz -r2 reads2.fastq.gz \
-a <reference_amplicon_seq> -g <sgRNA_seq>

### 🛠 Option 2: Manual Install  

**Requirements:**  
- 🐍 Python **3.9+** (Enhanced Edition upgraded from legacy Python 2.7)  
- ☕ Java **8+**  
- 🛠 GCC / make  
- ✂️ [Trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic)  
- 🔄 [FLASH](http://ccb.jhu.edu/software/FLASH/)  
- 🧬 Needle from the [EMBOSS suite](http://emboss.open-bio.org/)  

**Install via pip:**  
```bash
pip install crispresso-enhanced

CRISPResso \
  -r1 reads1.fastq.gz \
  -r2 reads2.fastq.gz \
  -a AATGTCCCCCAATGGGAAGTTCATCTGGCACTGCCCACAGGTGAGGAGGTCATGATCCCCTTCTGGAGCTCCCAACGGGCCGTGGTCTGGTTCATCATCTGTAAGAATGGCTTCAAGAGGCTCGGCTGTGGTT \
  -g TGAACCAGACCACGGCCCGT


