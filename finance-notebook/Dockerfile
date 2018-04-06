# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/scipy-notebook

MAINTAINER markusschanta <https://github.com/markusschanta>

USER root

# Install Python 3 packages
RUN conda install --yes \
    'altair' \
    'quandl' \
    'vega_datasets'

# Set up markusschanta/dotfiles
RUN rm .bashrc .profile && \
    cd /usr/local/src && \
    git clone https://github.com/markusschanta/dotfiles.git && \
    cd dotfiles && \
    ./install; exit 0

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
