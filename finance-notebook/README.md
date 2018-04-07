![docker pulls](https://img.shields.io/docker/pulls/markusschanta/finance-notebook.svg) ![docker stars](https://img.shields.io/docker/stars/markusschanta/finance-notebook.svg)

# Finance Jupyter Notebook Stack

## What it Gives You

* Fully-functional Jupyter Notebook (incl. JupyterLab)
* Preinstalled financial computing packages
  * altair
  * quandl
  * vega_datasets
* Preinstalled [markusschanta/dotfiles](https://github.com/markusschanta/dotfiles)
* All the features of the [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks) images

## Basic Use

The following command starts a container with the Notebook server listening for HTTP connections on port 8888 with a randomly generated authentication token configured.

```
$ docker run -it --rm -p 8888:8888 markusschanta/finance-notebook
```

Take note of the authentication token included in the notebook startup log messages. Include it in the URL you visit to access the Notebook server or enter it in the Notebook login form.

## Notebook Options

See the [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks) documentation for further supported options. This image should support all the features of the jupyter/docker-stacks images.

## Development Workflow

1. Run an interactive foreground container for a stack and test your changes:
```
$ make bash/finance-notebook
```
2. Build the container:
```
$ make build/finance-notebook
```
3. Push the container:
```
$ make push/finance-notebook
```

### Steps to reclaim disk space

```
sudo service docker stop
cd /var/lib/docker
sudo ls -l
sudo ncdu
df
sudo rm -rf overlay2
sudo rm -rf image
df
sudo service docker start
```
