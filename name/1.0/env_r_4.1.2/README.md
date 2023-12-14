# _**name**_ R 4.1.2 container

## Informations

Environment: [R](https://cran.r-project.org/) \
Version: 4.1.2

Description: **R environment with the different packages for the workflow: _name_**

r-base Docker Hub: [https://hub.docker.com/_/r-base](https://hub.docker.com/_/r-base)

## Citation

* **R**:  R Core Team (2021). R: A language and environment for statistical computing. R Foundation for Statistical Computing, Vienna, Austria. URL [https://www.R-project.org/](https://www.R-project.org/).
* **ggplot2**: H. Wickham. ggplot2: Elegant Graphics for Data Analysis. Springer-Verlag New York, 2016.
* **dplyr**: Hadley Wickham, Romain François, Lionel Henry, Kirill Müller and Davis Vaughan (2023). dplyr: A Grammar of Data Manipulation. R package version 1.1.4. [https://CRAN.R-project.org/package=dplyr](https://CRAN.R-project.org/package=dplyr)
* **tidyr**: Hadley Wickham, Davis Vaughan and Maximilian Girlich (2023). tidyr: Tidy Messy Data. R package version 1.3.0. [https://CRAN.R-project.org/package=dplyr](https://CRAN.R-project.org/package=tidyr)
* **magrittr**: Stefan Milton Bache and Hadley Wickham (2022). magrittr: A Forward-Pipe Operator for R. R package version 2.0.3. [https://CRAN.R-project.org/package=magrittr](https://CRAN.R-project.org/package=magrittr)

## Licence



## Build R 4.1.2 Docker image 

```bash
docker build . -t name_env_r:4.1.2 && docker tag name_env_r:4.1.2 name_env_r:latest
```

## Using R 4.1.2 container with interactive shell

To run an interactive shell
```bash
docker run -v /your/data/dir:/data -it name_env_r:tagname
```
After this command you work in the container. You can directly execute the different CD-HIT commands.

## Push to Docker Hub
1. Rename tool with username
```bash
docker tag name_env_r:tagname <user-name>/name_env_r:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/name_env_r:tagname
```

## Retrieve the image from Docker Hub

```bash
docker push jroussea/name_env_r:tagname
```
For example, to retrieve the latest version:
```bash
docker push jroussea/name_env_r:latest
```