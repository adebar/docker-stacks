![docker pulls](https://img.shields.io/docker/pulls/markusschanta/finance-notebook.svg) ![docker stars](https://img.shields.io/docker/stars/markusschanta/finance-notebook.svg)

# Finance Jupyter Notebook Stack

## What it Gives You

* Fully-functional Jupyter Notebook (incl. JupyterLab)
* Preinstalled financial computing packages
  * quandl
  * vega_datasets
* All the features of the [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks) images

## Basic Use

The following command starts a container with the Notebook server listening for HTTP connections on port 8888 with a randomly generated authentication token configured.

```
docker run -it --rm -p 8888:8888 markusschanta/finance-notebook
```

Take note of the authentication token included in the notebook startup log messages. Include it in the URL you visit to access the Notebook server or enter it in the Notebook login form.

## Notebook Options

See the [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks) documentation for further supported options. This image should support all the features of the jupyter/docker-stacks images.
