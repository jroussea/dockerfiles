# Diamond v2.1.8 container

## Informations

Main tool: [Diamond](https://github.com/bbuchfink/diamond/wiki) \
Version: 2.1.8

Description: **DIAMOND is a sequence aligner for protein and translated DNA searches, designed for high performance analysis of big sequence data.**

GitHub: [https://github.com/bbuchfink/diamond](https://github.com/bbuchfink/diamond)

## Citations

* Buchfink B, Reuter K, Drost HG, "Sensitive protein alignments at tree-of-life scale using DIAMOND", Nature Methods 18, 366–368 (2021). doi:10.1038/s41592-021-01101-x

For sequence clustering:

* Buchfink B, Ashkenazy H, Reuter K, Kennedy JA, Drost HG, "Sensitive clustering of protein sequences at tree-of-life scale using DIAMOND DeepClust", bioRxiv 2023.01.24.525373; doi: https://doi.org/10.1101/2023.01.24.525373

## License

[The original Diamond license still applies to this container](https://github.com/bbuchfink/diamond/blob/master/LICENSE)

## Build Diamond Docker image 

```bash
docker build . -t diamond:2.1.8 && docker tag diamond:2.1.8 diamond:latest
```

## Using Diamond

### General use

**Run the application**
```bash
docker run diamond:tagname diamond <options>
```
* *-v /your/data/dir* : directory containing the files that will be analyzed 
* *\<options_\>* : indicate the different options to use

### Example of use

* To get help
```bash
docker run diamond:tagname diamond
```

### Interactive shell

To run an interactive shell
```bash
docker run -it diamond:tagname
```
After this command you work in the container. You can directly execute the different Diamond commands.

## Push to Docker Hub
1. Rename tool with username
```bash
docker tag diamond:tagname <user-name>/diamond:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/diamond:tagname
```

## Retrieve the image from Docker Hub

```bash
docker pull <user-name>/diamond:tagname
```
