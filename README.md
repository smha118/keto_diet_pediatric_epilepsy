# Multiomics data analysis and code for ketogenic diet therapy for pediatric epilepsy 


This github page contains source code used for multiomics data analysis in <br>
"Ketogenic diet therapy for pediatric epilepsy 
is associated with alterations in the human gut microbiome 
that confer seizure resistance in mice"

Each directory contains donors & recipients data and relevant source codes in jupyter notebook format. Due to the size limit mmvec result files are stored in the [Google Drive](https://drive.google.com/drive/folders/1Z8sWRNHAHaUCh3hYm9MvkVGY32F4IZ1w?usp=sharing).

The overall schematic looks like below:<br>
After 3.Merge_module_info2mmvec_network_for_wkda, the output files were used in [Mergeomics](http://mergeomics.research.idre.ucla.edu/) webpage to perform wKDA analysis.
The results of wKDA were then used to modify the node description in 4.modify_mergeomics_results. 
After 4.modify_mergeomics_results, the results files were loaded onto the Cytoscape for further visualization.



```mermaid
flowchart TD;
	A[WGNCA] --> C[1.parse_mmvec]
	B[MMVEC] --> C[1.parse_mmvec]
	C-->D{WGCNA from RNA-seq data?}
	D -- Yes --> E[2.parse_wgcna_modules]
	D -- No --> F[3.Merge_module_info2mmvec_network_for_wkda]
	E --> F[3.Merge_module_info2mmvec_network_for_wkda]
	F --> G[Mergeomics]
	G --> H[4.modify_mergeomics_results]
```


