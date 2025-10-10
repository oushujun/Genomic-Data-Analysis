## Using Deep Learning to predict gene annotations

### Helixer GitHub ###
https://github.com/usadellab/Helixer  
https://github.com/gglyptodon/helixer-docker

### Running via Apptainer ###
Running Helixer via Apptainer was tested for the following versions recently:
- Apptainer v1.3.4 on Ubuntu 22.04 and Ubuntu 24.04 (with the extra setup command)
- Apptainer v1.3.6 on Ubuntu 22.04
```
# pull current docker image 
apptainer pull docker://gglyptodon/helixer-docker:helixer_v0.3.6_cuda_12.2.2-cudnn8

# in this example, the directory "helixer_test" already contains downloaded data
apptainer run --nv helixer-docker_helixer_v0.3.6_cuda_12.2.2-cudnn8.sif Helixer.py \
  --fasta-path helixer_test/Arabidopsis_lyrata.v.1.0.dna.chromosome.8.fa.gz --lineage land_plant \
  --gff-output-path Arabidopsis_lyrata_chromosome8_helixer.gff3
# notice '--nv' for GPU support
```
