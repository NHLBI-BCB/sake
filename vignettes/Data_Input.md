# Data_Input
Yu-Jui Ho and Toby Aicher  
`r Sys.Date()`  

There are three different ways you can upload files into `sake` pacakge. It can either be 

- Rawdata file 
- Preloaded data
- Saved run result

## Rawdata file

The gene count data file is one of the most common types of data format. Each row represents expression value from a gene, and each column represents transcriptome library derived from a single sample. The package requires the first row to be the header, which you can provide information about each sample. The first column is required to be names/ID for each gene/transcript. 

You can also specify the delimiter according to different file type.

- Tab (\\t) - Default setting for `.txt` or `.out` file
- Comma (,) - Usually used by `.csv` file
- Semicolon (;) - Not so common, but some use this type

Example data sets should look like this

Gene    |MEF-1    |MEF-10   |MEF-11   |MEF-12   |MEF-2
--------|---------|---------|---------|---------|-----
Gm15772 |1493.562 |1714.470 |1178.217 |1858.733 |1199.904
Dnajc3  |75.209   |67.320   |291.554  |49.924   |166.867
Mdn1    |29.288   |7.819    |82.620   |1.262    |0.214
Mfap1b  |4.796    |1.335    |4.308    |0.000    |0.748
Zglp1   |1.939    |78.381   |3.385    |0.541    |3.205
Gm12359 |1.225    |13.159   |1.846    |0.000    |0.320
Gm16039 |0.408    |2.861    |0.154    |0.360    |56.406
Gm11149 |0.204    |0.000    |0.000    |0.000    |0.000

## Preloaded data

There are several preloaded gene expression data from published single-cell studies that were already been preloaded with the package. They include studies relate to neuronal differentiation^[Treutlein *et al*, Dissecting direct reprogramming from fibroblast to neuron using single-cell RNA-seq, Nature, 2016] and circulating tumor cells in pancreatic cancer^[Ting *et al*, Single-Cell RNA Sequencing Identifies Extracellular Matrix Gene Expression by Pancreatic Circulating Tumor Cells, Cell Reports, 2014]. The user can sift through and test each module using these data.   

## Saved run result

User has the option to utlize [yabi](https://demo.bsr.tools/yabi/login/?next=/yabi/) to run clustering analysis through its user-friendlly web interface. This is especially useful when the sample sizes of the single-cell study becomes larger and larger. The previous run results can be saved in [.rda](https://stat.ethz.ch/R-manual/R-devel/library/base/html/load.html) format and then loaded back to `sake` package. Once the analysis is done, it will include data analysis of NMF, t-SNE, and DESeq2 (if specified). 

Example saved data can be downloaded [here](../data/Ting.NMF5.rda)

*** 

In this case, we will select data published from Ting *et al*. 

<img src="Figures/Ting/preload.png" width="800px" height="450px" />


A successfully loaded data will look like this  

<img src="Figures/Ting/loaded_file.png" width="800px" height="450px" />

***

Continue on the next section [Quality Control](Quality_Control.Rmd)

*** 

> "*If you are thinking without writing, you only think your're thinking* - Leslie Lamport"
([via](https://www.youtube.com/watch?v=-4Yp3j_jk8Q))