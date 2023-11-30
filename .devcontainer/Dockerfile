FROM jupyter/r-notebook:ubuntu-22.04

USER root

RUN apt-get update && \
    apt-get install -y gdebi-core && \
    wget https://download2.rstudio.org/server/jammy/amd64/rstudio-server-2023.09.1-494-amd64.deb && \
    gdebi -n rstudio-server-2023.09.1-494-amd64.deb

USER ${NB_UID}

RUN pip install --no-cache-dir jupyter-rsession-proxy==2.2.0
# RUN /opt/conda/bin/R --silent --slave --no-save --no-restore -e "install.packages('languageserver', repos='https://cran.r-project.org/')"