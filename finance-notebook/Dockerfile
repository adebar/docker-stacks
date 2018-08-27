# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/scipy-notebook

MAINTAINER markusschanta <https://github.com/markusschanta>

USER root

# Disable git's "push.default unset" warning
RUN git config --global push.default simple

# Install packages
RUN apt-get update && apt-get install -y \
    imagemagick \
    less \
    ssh \
    && rm -rf /var/lib/apt/lists/*

# Install JupyterLab extensions
RUN jupyter labextension install @jupyterlab/celltags
RUN jupyter labextension install @jupyterlab/git
# RUN jupyter labextension install @jupyterlab/shortcutui
RUN jupyter labextension install @jupyterlab/statusbar
RUN jupyter labextension install @jupyterlab/toc
RUN jupyter labextension install @jupyterlab/vega3-extension
# Install JupyterLab Voyager extension
# This extension can be a bit flakey with the requirements, comment out if this
# step fails
# RUN jupyter labextension install jupyterlab_voyager --debug

# Install Python 3 packages that are not in conda
RUN pip install \
    shub \
    vdom

# Install Python 3 packages
RUN conda install --yes \
    'altair' \
    'boto3' \
    'quandl' \
    'pandas-profiling' \
    'scrapy' \
    'vega_datasets'

# Set up markusschanta/dotfiles
RUN rm .bashrc .profile && \
    cd /usr/local/src && \
    git clone https://github.com/markusschanta/dotfiles.git && \
    cd dotfiles && \
    ./install; exit 0

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
