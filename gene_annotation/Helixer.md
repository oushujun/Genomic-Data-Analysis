## Using Deep Learning for ab initio gene predictions

### Helixer GitHub ###
This is the original Helixer that includes model training and prediction  
https://github.com/usadellab/Helixer  
https://github.com/gglyptodon/helixer-docker  

### HelixerLite GitHub ###
This is a lightweight and easy-to-install Helixer that only includes model prediction  
https://github.com/nextgenusfs/helixerlite  

### Install HelixerLite ###
```
conda create -n helixer python=3.10  
conda activate helixer  
python -m pip install helixerlite
```

### Annotate Arabidopsis sequences with different models ###
#### 1. request compute resources ####
```
sinteractive -A PAS3124 -n 60 -t 1:00:00
```

#### 2. use HelixerLite to predict genes using varying models ####
```
nohup helixerlite --fasta Arabidopsis_thaliana.TAIR10.dna.toplevel.chr1_5M.fa --lineage land_plant --out chr1_5M.land_plant.output.gff3 -c 30 &  
nohup helixerlite --fasta Arabidopsis_thaliana.TAIR10.dna.toplevel.chr1_5M.fa --lineage fungi --out chr1_5M.fungi.output.gff3 -c 30 &  
nohup helixerlite --fasta Arabidopsis_thaliana.TAIR10.dna.toplevel.chr1_5M.fa --lineage vertebrate --out chr1_5M.vertebrate.output.gff3 -c 30 &  
nohup helixerlite --fasta Arabidopsis_thaliana.TAIR10.dna.toplevel.chr1_5M.fa --lineage invertebrate --out chr1_5M.invertebrate.output.gff3 -c 30 &
```

### Download and Install IGV ###
https://igv.org/download/html/oldtempfixForDownload.html
