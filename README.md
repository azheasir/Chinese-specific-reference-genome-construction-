# Chinese specific reference genome construction
The following content presents the experimental data, process, and results of the article "Chinese specific reference gene construction based on large scale population genetic variations"

Please let us know, if you find mistakes or want your tool added.
#Get tools
Information how to install 'conda' and add the 'bioconda' channel is available on https://bioconda.github.io/.
```Bash
conda create --name sv python=3.6
source activate sv
conda install simuG== bwa==  samtools==  qualimap==  
```
# Get data
1.Download variant fragments(Taking downloading SNV samples as an example)
```Bash
wget -c http://ftp.1000genomes.ebi.ac.uk/vol1/ftp/data_collections/HGSVC2/release/v1.0/integrated_callset/freeze3.snv.alt.vcf.gz
```
2.Extract Asian samples from the downloaded variant fragments file and add AC AN columns
```Bash
bcftools view -s HG00512,HG00513,NA18939,HG00864,NA18534,HG01596 -o eastAisa.snv.alt.vcf freeze3.snv.alt.vcf
```
3.Download Grch38 reference genome
```Bash
wget -c https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000001405.26/GCF_000001405.26_GRCh38_genomic.fna.gz
```
4.Download genomic samples from the three ethnic groups of Han in the north, Han in the south, and Dai(NA18525、NA18644、NA18757、NA18747、NA18561；HG00458、HG00717、HG00476、HG00534、HG00716；HG00759、HG01799、HG01028、HG02389、HG01812,Taking downloading NA18525 as an example))
```Bash
wget -c 	ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR741/SRR741372/SRR741372_1.fastq.gz
wget -c 	ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR741/SRR741372/SRR741372_2.fastq.gz
wget -c   ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR741/SRR741373/SRR741373_1.fastq.gz
wget -c   ftp://ftp.sra.ebi.ac.uk/vol1/fastq/SRR741/SRR741373/SRR741373_2.fastq.gz
```
