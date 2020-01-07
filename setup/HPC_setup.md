# HPC setup

## Containers / Docker
### Docker (local)
install instructions for docker on os x are here:
https://docs.docker.com/docker-for-mac/install/

### Containers
where possible check that all final analyses can run within containers. 
Several containers are setup for general use and available from dockerhub. 
Most containers start from a base of the broadinstitute's GATK docker

These can be individually run as follows:

    docker pull broadinstitute/gatk:4.1.1.0
    docker run -v ${PWD}:/gatk/work/ -it broadinstitute/gatk

    docker pull broadinstitute/genomes-in-the-cloud:2.3.1-1512499786
    docker run -v ${PWD}:/usr/gitc/work/ -it broadinstitute/genomes-in-the-cloud:2.3.1-1512499786

    docker pull sethnr/ivbd_vecgen:191004
    docker run -v ${PWD}/work/:/root/work -it sethnr/ivbd_vecgen:191004
    
setup for all our dockers should be copied into the 'containers' folder in this git

### Singularity (on M3/MASSIVE)
The slurm cluster uses singularity rather than docker, this is preinstalled and can be activated by:

    module load singularity

## Snakemake
longer pipelines should be written in snakemake, unless you've a great reason for doing this in nextflow/wdl. 
for preference, all snakemake pipelines should use one of the available docker containers, or one of your own creation. 
snakemake is best installed via conda (see python_setup). Once installed type 

    conda install snakemake
    snakemake -v

a snakemake tutorial is available here:
https://snakemake.readthedocs.io/en/stable/tutorial/tutorial.html
