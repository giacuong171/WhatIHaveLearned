---
URL: https://nexco.ch/blog/What-is-Spatial-Transcriptomics
---
### A brief history of spatial transcriptomics

Today, the term spatial transcriptomics largely implies quantifying gene expression in a spatial context for large numbers of genes or on a transcriptome-wide scale. But, the journey to this point began over 50 years ago, when a method called in situ hybridization (ISH) was developed to visualize individual genes directly on tissue sections (1).

Throughput gradually increased with the development of single-molecule fluorescent in situ hybridization (smFISH) (2, 3), but the major breakthrough arrived in 2016 when researchers positioned histological sections on barcoded array slides to finally provide transcriptome-wide spatial read-outs, albeit not at single-cell resolution (4). This technology led to the Visium product developed by [10X Genomics](https://www.10xgenomics.com/spatial-transcriptomics).

Subsequent breakneck innovation in the field and its promise of transforming biological insight in every imaginable area of tissue biology have led to the crowning of spatial transcriptomics as Method of the Year 2020 by Nature Methods (5).

### The exciting spatial transcriptomic methods of today

The holy grail of present-day spatial transcriptomic technologies is to provide users with three core capabilities: transcriptome-wide profiling, at single-cell resolution, with high gene-detection efficiency. Current technologies generally fall short of achieving all of these goals, but development continues at pace (6). Technologies can largely be split into four broad categories each with different levels of resolution, throughput, and specificity.

#### 1. Region of interest (ROI) selection followed by sequencing

Specific locations in a tissue can be isolated by laser capture microdissection followed by bulk or scRNA-seq. ROI can also be optically selected with the GeoMX™ Digital Spatial Profiler combined with the Human Whole-Transcriptome Atlas from [Nanostring](https://nanostring.com/products/geomx-digital-spatial-profiler/geomx-rna-assays/geomx-whole-transcriptome-atlas/), which uses UV light to release antibody-bound photocleavable targeted gene barcodes for quantification of over 18,000 genes by nCounter or next generation sequencing (NGS). This technology does not yet provide single-cell resolution.

#### 2. Single-molecule FISH

Adaptations of classical smFISH have led to a dramatic increase in the number of genes quantifiable with this technique in the spatial context. For instance, RNA seqFISH+ can image mRNAs for up to 10,000 genes in diverse tissue samples (7). Similarly, multiplexed error-robust FISH (MERFISH) uses combinatorial binary barcoding and sequential rounds of smFISH imaging to read complete mRNA identifiers and infer expression levels for thousands of genes at the single-cell resolution (8). Both technologies are imaging-based and do not require sequencing.

#### 3. In situ sequencing (ISS)

ISS also allows the targeted analysis of short RNA fragments directly in morphologically preserved cells and tissue but uses dual padlock probes containing a gene-specific barcode sequence (9). These probes undergo rolling circle amplification followed by successive rounds of fluorescent probe hybridization, imaging, and removal to generate an optical signature of gene expression for a few hundred genes at single-cell resolution without requiring NGS. The system is now known as Xenium and is produced by [10X Genomics](https://www.10xgenomics.com/spatial-transcriptomics) .

#### 4. Next-generation sequencing with spatial barcoding

Perhaps the most popular spatial transcriptomic method to date is Visium, also produced by 10X Genomics . This technology relies on positioning tissue sections on slides printed with spots harboring reverse transcription primers encoding positional barcodes to record each transcript location, unique molecular identifiers to adjust for duplicate sequences arising from amplification, and poly-T oligonucleotides to capture localized polyadenylated mRNA transcripts in an unbiased transcriptome-wide manner. NGS of these sequences is then performed with expression data spatially overlayed on tissue images.

While Visium provides unbiased transcriptome-wide information, it does not have single-cell spatial resolution and limits the size of tissue sections that can be profiled. In contrast, spatial enhanced resolution omics-sequencing (Stereo-seq) developed by BGI uses barcoded DNA nanoball-patterned arrays to provide a much higher number of spots, increasing unbiased transcriptome-wide resolution to the single-cell level on larger tissue sections than previously possible (10).

### **Data analysis for spatial transcriptomics**

Each of the methods discussed above comes with intricate data processing and analysis requirements to generate robust, reliable, and reproducible results that drive crucial decision points in a project lifespan, from drug discovery pipelines to large-scale spatial gene expression atlases.

Data analysis problems such as image preprocessing, cell-type deconvolution of NGS barcoding data, integration of targeted spatial transcriptomic data with scRNA-seq data sets, statistical inference of spatially variable genes, and assessment of cell-cell interactions, not to mention the vast storage requirements of images and sequencing data all benefit from bespoke analysis approaches instead of out-of-the-box tools depending on the research question (11).

For instance, plug-and-play data analysis tools such as Space Ranger from 10X Genomics provide a good starting point to analyze Visium data but lack capabilities to directly integrate scRNA-seq data to provide an inferred single-cell resolution that may reveal hidden layers of potentially useful information.

Similarly, most spatial transcriptomic analysis packages do not have options for the analysis of repetitive sequences derived from transposable elements. These core components of the ‘dark genome’ comprise a staggering fraction of standard mRNA-seq libraries but are routinely omitted due to difficulties in mapping highly repetitive sequences (12). As key components of normal development, core biological processes, and disease, transposable elements represent a vast, untapped resource of spatially resolved tissue and disease biomarkers potentially influencing tissue microenvironments in as yet undiscovered ways (13).