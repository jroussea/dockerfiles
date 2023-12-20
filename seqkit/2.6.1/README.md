# SeqKit v2.6.1 container

## Informations

Main tool: [SeqKit](https://bioinf.shenwei.me/seqkit/) \
Version: 2.6.1

Description: **SeqKit - a cross-platform and ultrafast toolkit for FASTA/Q file manipulation**

GitHub: [https://github.com/shenwei356/seqkit](https://github.com/shenwei356/seqkit) 

## Citation

* W Shen, S Le, Y Li*, F Hu*. SeqKit: a cross-platform and ultrafast toolkit for FASTA/Q file manipulation. PLOS ONE. doi:10.1371/journal.pone.0163962. 

## License

[The original SeqKit license still applies to this container](https://github.com/shenwei356/seqkit/blob/master/LICENSE)

## Build SeqKit Docker image

```bash
docker build . -t seqkit:2.6.1  && docker tag seqkit:2.6.1 seqkit:latest
```

## Using SeqKit

### General use

**Run the application**
```bash
docker run -v /your/data/dir:/data seqkit:tagname <seqkit-command-name> <options>
```
* *-v /your/data/dir* : directory containing the files that will be analyzed 
* *\<seqkit-command-name\>* : specify the seqkit command to use (example: seq, stats, split, ...) 
* *\<options_\>* : indicate the different options to use

### Example of use

* To get help
```bash
docker run seqkit:tagname \<seqkit-command-name\> --help
```
* Example of use: split a fasta file into several files containing 10000 sequences
```bash
docker run -v your/data/directory:/data seqkit:tagname split2 input.fa -o output -f -s 10000
```

### Interactive shell

To run an interactive shell
```bash
docker run -v /your/data/dir:/data -it seqkit:tagname
```
After this command you work in the container. You can directly execute the different SeqKit commands.

## Push to Docker Hub

1. Rename tool with username
```bash
docker tag seqkit:tagname <user-name>/seqkit:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/seqkit:tagname
```

## Retrieve the image from Docker Hub

```bash
docker pull <user-name>/seqkit:tagname
```
