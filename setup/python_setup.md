prerequisites:
  python3 (obvs)
  miniconda
  jupyter notebook

essential libs:
  numpy
  pandas
  scikit
  scikit-learn
  scikit-allel
  
== miniconda / jupyter ==
full install instructions available at:  
  https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html  
  https://jupyter.readthedocs.io/en/latest/install.html  

quickstart:  
>  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh  
  chmod 755 Miniconda3-latest-Linux-x86_64.sh  
   ./Miniconda3-latest-Linux-x86_64.sh  

>  conda config --prepend pkgs_dirs /home/${USER}/.conda/pkgs  
  conda config --prepend envs_dirs /home/${USER}/.conda/envs  
  conda config --add channels defaults  
  conda config --add channels bioconda
  conda config --add channels conda-forge

if jupyter isn't installed already, type something like:
>  conda install jupyter
  
then try:
>  jupyter notebook
