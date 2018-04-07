# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/scipy-notebook

MAINTAINER markusschanta <https://github.com/markusschanta>

USER root

# Install packages
RUN apt-get update && apt-get install -y \
    imagemagick \
    less \
    ssh \
    && rm -rf /var/lib/apt/lists/*

# Install Python 3 packages
RUN conda install --yes \
    'altair' \
    'quandl' \
    'scrapy' \
    'vega_datasets'

RUN pip install shub

# Set up markusschanta/dotfiles
RUN rm .bashrc .profile && \
    cd /usr/local/src && \
    git clone https://github.com/markusschanta/dotfiles.git && \
    cd dotfiles && \
    ./install; exit 0

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
