# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/scipy-notebook

MAINTAINER adebar <https://github.com/adebar>

USER root

# Install Python 3 packages
RUN conda install --yes \
    'quandl' \
    'vega_datasets'

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_USER
