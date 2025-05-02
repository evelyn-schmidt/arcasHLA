FROM continuumio/miniconda3:latest

WORKDIR /app

# Install Git LFS
RUN apt-get update && \
    apt-get install -y git curl pigz
RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash
RUN apt-get install -y git-lfs

#RUN git clone -b v0.6.0 https://github.com/RabadanLab/arcasHLA.git
RUN git clone https://github.com/evelyn-schmidt/arcasHLA.git
RUN conda env create -f /app/arcasHLA/environment.yml
RUN echo "source activate arcas-hla" > ~/.bashrc
ENV PATH /opt/conda/envs/arcas-hla/bin:$PATH

#ADD dat/ /app/arcasHLA/dat/
# Make all files readable
#RUN chmod -R +r /app/arcasHLA/dat/
# Additionally, add execute permissions to all directories
#RUN find /app/arcasHLA/dat/ -type d -exec chmod +x {} \;
