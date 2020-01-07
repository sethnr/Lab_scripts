#Download base image ubuntu 16.04
FROM broadinstitute/gatk:4.1.3.0

#update 
#RUN apt-get install apt-transport-https
#RUN add-apt-repository 'deb http://cloud.r-project.org/bin/linux/ubuntu bionic-cran36/'
#RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9

RUN apt-get update

#create installs / setup dir
WORKDIR /root/ 
RUN mkdir ./installs
WORKDIR ./installs 
RUN mkdir setup
COPY shortcuts.sh setup/shortcuts.sh
RUN cat setup/shortcuts.sh >> ~/.bashrc

#minimap2
WORKDIR /root/
RUN apt-get -y install git
WORKDIR ./installs
RUN git clone https://github.com/lh3/minimap2 
WORKDIR ./minimap2 
RUN pwd
RUN git checkout v2.3
RUN make && chmod 755 minimap2 
RUN mv minimap2 /usr/bin/minimap2

#bwa
WORKDIR /root/
RUN apt-get install bwa

#picard
WORKDIR /root/
RUN mkdir ./installs/picard
WORKDIR ./installs/picard
RUN wget https://github.com/broadinstitute/picard/releases/download/2.20.8/picard.jar
RUN mv picard.jar /jars/picard.jar  
ENV PICARD /jars/picard.jar
#evorha
WORKDIR /root/
COPY evorha.jar  /jars/evorha.jar

#emacs
WORKDIR /root/
RUN apt-get -y install emacs

#R (check updated apt-get)
# WORKDIR /root/
# WORKDIR ./installs
# RUN apt install r-base r-base-core r-recommended
# COPY install_R_packages2.R  install_R_packages2.R 
# RUN Rscript install_R_packages2.R

#Python
WORKDIR /root/
RUN conda install -c bioconda pyvcf

