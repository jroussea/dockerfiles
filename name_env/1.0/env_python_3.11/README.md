# _**name**_ Python 3.11.5 container

## Informations

Environment: [Python](https://www.python.org/) \
Version: 3.11.5

Description: **Python environment with the different modules for the workflow: _name_**

Python Docker Hub: [https://hub.docker.com/_/r-base](https://hub.docker.com/_/python)

## Citation

* **Python**: Van Rossum, G., & Drake Jr, F. L. (1995). Python reference manual. Centrum voor Wiskunde en Informatica Amsterdam.
* **Pandas**: The pandas development team. (2020). pandas-dev/pandas: Pandas. Zenodo. version latest, DOI [10.5281/zenodo.3509134](10.5281/zenodo.3509134), URL [https://doi.org/10.5281/zenodo.3509134](https://doi.org/10.5281/zenodo.3509134)

## Licence



## Build Python 3.11 Docker image 

```bash
docker build . -t name_env_py:3.11 && docker tag name_env_py:3.11 name_env_py:latest
```

## Using Python 3.11ontainer with interactive shell

To run an interactive shell
```bash
docker run -v /your/data/dir:/data -it name_env_py:tagname
```
After this command you work in the container. You can directly execute the different CD-HIT commands.

## Push to Docker Hub
1. Rename tool with username
```bash
docker tag name_env_py:tagname <user-name>/name_env_py:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/name_env_py:tagname
```

## Retrieve the image from Docker Hub

```bash
docker push jroussea/name_env_py:tagname
```
For example, to retrieve the latest version:
```bash
docker push jroussea/name_env_py:latest
```

