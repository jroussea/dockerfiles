# CD-HIT v4.8.1 container

## Informations

Main tool: [CD-HIT](https://sites.google.com/view/cd-hit) \
Version: 4.8.1

Description: **Cd-hit: a fast program for clustering and comparing large sets of protein or nucleotide sequences**

GitHub: [https://github.com/weizhongli/cdhit](https://github.com/weizhongli/cdhit) 

## Citations

1. Weizhong Li & Adam Godzik. Cd-hit: a fast program for clustering and comparing large sets of protein or nucleotide sequences. Bioinformatics (2006) 22:1658-1659 
2. Limin Fu, Beifang Niu, Zhengwei Zhu, Sitao Wu and Weizhong Li, CD-HIT: accelerated for clustering the next generation sequencing data. Bioinformatics, (2012), 28 (23): 3150-3152. doi: 10.1093/bioinformatics/bts565

## License

[The original CD-HIT license still applies to this container](https://github.com/weizhongli/cdhit/blob/master/license.txt)

## Build CD-HIT Docker image 

```bash
docker build . -t cd-hit:4.8.1 && docker tag cd-hit:4.8.1 cd-hit:latest
```

## Using CD-HIT

### General use

**Run the application**
```bash
docker run -v /your/data/dir:/data cd-hit:tagname <cd-hit-command-name> <options>
```
* *-v /your/data/dir* : directory containing the files that will be analyzed 
* *\<cd-hit-command-name\>* : specify the cd-hit command to use (example: cd-hit, cd-hit-est, cd-hit-454, ...) 
* *\<options_\>* : indicate the different options to use

### Example of use

* To get help
```bash
docker run cd-hit:tagname cd-hit
```
* Clustering with 90% identity
```bash
docker run -v /your/data/dir:/data cd-hit:tagname cd-hit -i input.fa -o output -c 0.9 -n 5 -d 0
```

### Interactive shell

To run an interactive shell
```bash
docker run -v /your/data/dir:/data -it cd-hit:tagname
```
After this command you work in the container. You can directly execute the different CD-HIT commands.

## Push to Docker Hub
1. Rename tool with username
```bash
docker tag cd-hit:tagname <user-name>/cd-hit:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/cd-hit:tagname
```

## Retrieve the image from Docker Hub

```bash
docker pull <user-name>/cd-hit:tagname
```
