
### Create and activate the environment.
```
mamba env create -f synteny.yml 
conda activate synteny
```
### Clone the repo. 
```
git clone https://github.com/cwb14/synLTR.git
```
### Get the genomes. 
```
# Arabidopsis thaliana.
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/001/735/GCF_000001735.4_TAIR10.1/GCF_000001735.4_TAIR10.1_genomic.fna.gz && gunzip GCF_000001735.4_TAIR10.1_genomic.fna.gz && mv GCF_000001735.4_TAIR10.1_genomic.fna Athal.fa

# Arabidopsis halleri.
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/964/271/285/GCA_964271285.1_ddAraHall_1.3/GCA_964271285.1_ddAraHall_1.3_genomic.fna.gz && gunzip GCA_964271285.1_ddAraHall_1.3_genomic.fna.gz && mv GCA_964271285.1_ddAraHall_1.3_genomic.fna Ahall.fa

# Capsella bursa-pastoris.
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/036/452/645/GCA_036452645.1_ASM3645264v1/GCA_036452645.1_ASM3645264v1_genomic.fna.gz && gunzip GCA_036452645.1_ASM3645264v1_genomic.fna.gz && mv GCA_036452645.1_ASM3645264v1_genomic.fna Cburs.fa
```

### Get the refrence protein file. 
```
# Arabidopsis thaliana.
wget https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/001/735/GCF_000001735.4_TAIR10.1/GCF_000001735.4_TAIR10.1_protein.faa.gz && gunzip GCF_000001735.4_TAIR10.1_protein.faa.gz && mv GCF_000001735.4_TAIR10.1_protein.faa Athal.pep
```
### Run the syntenic analysis.
```
python synLTR/module1.py --genomes *fa --threads 50 --dir_name results --protein_fa Athal.pep --miniprot_outn 5 --script_dir synLTR/module1/
```
