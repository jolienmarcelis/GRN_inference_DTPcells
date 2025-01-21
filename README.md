# GRN_inference_DTPcells

This repository contains files and notebooks related to gene regulatory network (GRN) inference to unravel regulatory mechanisms driving drug-tolerant persister cells. Below is an overview of the repository structure.

To execute the files, a few data files are required: scRNA-seq data on persister cells and its associated metadata. 
- The count matrix (GSE150949_pc9_count_matrix.csv.gz) and the associated metadata file (GSE150949_metaData_with_lineage.txt.gz) can be retrieved from https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE150949
- Metadata containing the majority fate are retrieved from https://github.com/yaaraore/watermelon


---

1_Data_preprocessing:
This folder contains notebooks for data preprocessing and data exploration.

	1. scRNAseq_data_preprocessing.ipynb
	   - Implements the data preprocessing pipeline.
	   - Follows the CellOracle tutorial for preprocessing steps required for GRN inference.

	2. Metadata_analysis.ipynb
	   - Analyzes cell metadata, focusing on lineage barcodes and potential retrieval of cell fate from lineage barcodes.

	3. Analysis_preprocesses_metadata_paper.ipynb
	   - Compares lineage barcodes from different metadata files.

	4. PCA_analysis.ipynb
	   - Performs principal component analysis on preprocessed data.
	   - Plots data along the first and second principal components.
	   - Checks for correlation between the top principal components and the time point.

	5. Quality_control.ipynb
	   - Contains additional checks to assess the quality of the data.
	   - Steps are exploratory and not part of the required preprocessing for GRN inference with CellOracle.

	6. Persister_data_exploration_batch_correction.ipynb
	   - Data preprocessing pipeline but with implementation of BBKNN batch correction	

	7. Preprocessing_pipeline.ipynb
	   - Preprocesses data, with options to select a subset for preprocessing.

	8. Plots_for_report.ipynb
	   - Generates plots of force-directed graphs suitable for reports.



2_Predict_cell_fates: This folder is dedicated to predicting cell fates using a classification model.

	1. classification_model_cell_fate.ipynb
	   - Develops a classification model to predict cell fates based on gene signatures.


3_GRN_construction: This folder focuses on constructing context-specific GRNs using CellOracle and analyzing the inferred networks.

	1. CellOracle_workflow.ipynb
	   - Constructs context-specific GRNs using the CellOracle workflow.

	2. Network_analysis.ipynb
	   - Comparative analysis of the inferred GRNs (focusing on persister-subtype specific GRNs based on day-14 cells).


---

The most important files for continuation of the project are 1) scRNAseq_data_preprocessing.ipynb and/or Preprocessing_pipeline.ipynb to preprocess the data, 2) classification_model_cell_fate.ipynb to predict cell fates, 3) CellOracle_workflow.ipynb to infer context-specific GRNs, and 4) Network_analysis.ipynb to perform a comparative analysis of the inferred GRNs.
