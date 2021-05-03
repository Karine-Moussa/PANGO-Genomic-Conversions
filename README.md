# PANGO COVID-19 Mutation Conversion Tool:  Genetic  to Genomic Coordinates

> Mackenzie Sennett<sup>1</sup>, Kyle McGovern<sup>1</sup>, Karine Moussa<sup>1,2</sup>
1. Script Development
2. Software Note

## Summary
We developed a [python script](https://colab.research.google.com/drive/1gNQ5P8fsHWdLLjNbvY-Rp8QqqCxp-d-b?usp=sharing) to return the genomic coordinates of [PANGO amino acid mutations](https://cov-lineages.org/index.html), which are formatted in gene coordinates. We also deliver a notebook to return the [all genomic coordinates of  variants across all PANGO lineages](https://colab.research.google.com/drive/1vVDWNRcZ7AsO27n2SXaO9eww96ZwE2nz?usp=sharing).  


## Background
The PANGO lineage repository retreives sequence information from [GISAID](https://www.gisaid.org) to  identify COVID-19 lineages. Lineages are determined by monitoring groups of mutations involved in epidemoloigcal events.  

The current PANGO mutation format specfies the **genetic position** of an amino acid position (in amino acid coordinates, ie. 1 coordinate = 3 base pairs). 


<center><img width="300" alt="image" src="https://i.imgur.com/KkzFvWF.png" ></center>

<br></br>

What is needed for much of COVID-19 research is the **genomic position** of the amino acid mutation.

<center><img width="800" alt="image" src="https://i.imgur.com/lLPD6M5.png"></center>
<br></br>

## Notebook
Our manual-input conversion tool can be accessed here: [COVID-19 Variant Conversion Utility](https://colab.research.google.com/drive/1gNQ5P8fsHWdLLjNbvY-Rp8QqqCxp-d-b?usp=sharing)

This notebook uses SARS-CoV-2 genome [(zip file](https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/009/858/895/GCF_009858895.2_ASM985889v3/GCF_009858895.2_ASM985889v3_genomic.fna.gz)) and the variant gff ([zip file](https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/009/858/895/GCF_009858895.2_ASM985889v3/GCF_009858895.2_ASM985889v3_genomic.gff.gz)) to convert the genetic position of a PANGO mutation to its genomic location.

The genomic position is checked by translating the codon at the genomic position and verifying it against the reference amino acid of the input mutation.  

### Instructions:
- In the colab menu: *Runtime > Runall*
- In the **Input** section, enter mutation(s) of interest in PANGO format (then hit `enter`)
  - `[GENE]:[REF_AMINO_ACID][AMINO_ACID_LOC][ALT_AMINO_ACID]`
  - Example: `S:D1118H`
 -  **Note:** do not include mutation type
  --- ie: ~~`aa:`~~`S:D1118H`

### Example:
*`Runtime > Run all`*

<img width="500" alt="image" src="https://i.imgur.com/i0uICEG.png">
<br></br>

`Input PANGO mutations`

<img width="400" alt="image" src="https://i.imgur.com/44yNWP0.png">


`Output`

<img width="600" alt="image" src="https://i.imgur.com/0kYgZaj.png">



## Notebook: All Pango Lineage Conversions
We have written an additional notebook to return the genomic coordinates of all mutations across each lineage ([B.1.1.7](https://cov-lineages.org/global_report_B.1.1.7.html), [B.1.351](https://cov-lineages.org/global_report_B.1.351.html), [P.1](https://cov-lineages.org/global_report_P.1.html), [A.23.1](https://cov-lineages.org/global_report_A.23.1.html), [B.1.525](https://cov-lineages.org/global_report_B.1.525.html)). The utility searches each PANGO lineage web page to provide an up-to-date lists of variants.

The PANGO genomic coordinates notebook can be accessed here: [PANGO Lineages: All Genetic to Genomic conversions](https://colab.research.google.com/drive/1vVDWNRcZ7AsO27n2SXaO9eww96ZwE2nz?authuser=4#scrollTo=ASVUg4pLX9eV) 

### Instructions:
- In the colab menu: *Runtime > Runall*

`Preview of output`

<img width="800" alt="image" src="https://i.imgur.com/9C6imjo.png">

<br></br>
To download the output table, go to the Colab *files* tab > right-click on `snpaa.csv` > select *download*:

<img width="200" alt="image" src="https://i.imgur.com/pNNC5YU.png">

