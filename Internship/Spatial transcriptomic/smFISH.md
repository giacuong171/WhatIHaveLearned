---
URL: https://www.youtube.com/watch?v=sVVFxsF6Ahg
---

## Single Molecule Fluorescence
![[Pasted image 20240313160331.png]]

## Principles of smFIsh
- smFISH uses a set of short, fluoresccently labeled oligonucleotide probes that bind to specific target RNA molecules 
	 -> RNA profiles 
	 -> Probes must be designed to be complementary to the target RNA
	 -> The fluorescent probes generate a signal that can be visualized using fluorecence microscopy
## Why smFISH for studying gene expression
- High sensitivity: enables the detection of individual RNA molecules
- Single cell resolution: Examination of gene expression patterns at the single cell level -> insights into cellular heterogeneity
- Quantitative analysis
- Spatial information
## Analyzing smFISH data
- **Depends on research question**
- General workflow
	1. Spot and Cluster detection : Detect individual spots or cluster corresponding to the bound fluorescent probes
	2. Cellular and nuclear segmentation: Crucial for assigning spots to specific cellular compartments and extracting cell-specific information (**Cellpose**, **Stardust** -> nuclear segmentation )
	3. Statistical analsis: such as average distance of mRNA spots from the cell boundary, proportion of mRNA spots within the nucleaus versus the cytoplasm. 
		![[Pasted image 20240313162037.png]]
	4. Visualization and interpretation ![[Pasted image 20240313162204.png]]