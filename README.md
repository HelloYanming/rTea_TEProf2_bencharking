This repository is designed to evaluate the performance of **TEProf2** on simulation data.

The TEProf2 code has been adapted from the original implementation available at https://github.com/twlab/TEProf2Paper. These modifications were made to ensure compatibility with the updated versions of the Gencode GTF reference file and the Repeatmasker file.

**How to prepare Gencode GTF reference file**

1. Download Gencode version GTF reference file
   https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_37/gencode.v37.basic.annotation.gtf.gz
   
2. Sort the File
   
```
cat <GENCODE GTF>  | awk '{if($3=="transcript"||$3=="exon"||$3=="start_codon"){print}}' |  awk -F "; " '{print $0"\t"$2}' > <OUTPUT_sorted.gtf>`
```

3. Use custom script to create dictionary
   
```
genecode_to_dic.py <OUTPUT_sorted.gtf>
```

**How to prepare Repeatmasker file**
