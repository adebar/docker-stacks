# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/scipy-notebook

MAINTAINER adebar <https://github.com/adebar>

USER root

# Install Python 3 packages
RUN conda install --yes \
    'quandl' \
    'vega_datasets'

# Set up markusschanta/dotfiles
RUN rm .bashrc .profile
RUN git clone https://github.com/markusschanta/dotfiles.git && cd dotfiles && ./install; exit 0

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
