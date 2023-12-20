# InterProScan v5.65-97.0 container

## Informations

Main tool: [InterProScan](https://interproscan-docs.readthedocs.io/en/latest/) \
Version: 5.65-97.0

Description: **InterProScan 5: genome-scale protein function classification**

GitHub (tool): [https://github.com/ebi-pf-team/interproscan](https://github.com/ebi-pf-team/interproscan) 
GitHub (documentation): [https://github.com/ebi-pf-team/interproscan-docs/tree/master](https://github.com/ebi-pf-team/interproscan-docs/tree/master)

## Citation

**InterPro:** \
* The InterPro protein families and domains database: 20 years on Matthias Blum, Hsin-Yu Chang, Sara Chuguransky, Tiago Grego, Swaathi Kandasaamy, Alex Mitchell, Gift Nuka, Typhaine Paysan-Lafosse, Matloob Qureshi, Shriya Raj, Lorna Richardson, Gustavo A Salazar, Lowri Williams, Peer Bork, Alan Bridge, Julian Gough, Daniel H Haft, Ivica Letunic, Aron Marchler-Bauer, Huaiyu Mi, Darren A Natale, Marco Necci, Christine A Orengo, Arun P Pandurangan, Catherine Rivoire, Christian J A Sigrist, Ian Sillitoe, Narmada Thanki, Paul D Thomas, Silvio C E Tosatto, Cathy H Wu, Alex Bateman, Robert D Finn Nucleic Acids Research (2020), gkaa977, PMID: 33156333

**InterProScan:** \
* InterProScan 5: genome-scale protein function classification Philip Jones, David Binns, Hsin-Yu Chang, Matthew Fraser, Weizhong Li, Craig McAnulla, Hamish McWilliam, John Maslen, Alex Mitchell, Gift Nuka, Sebastien Pesseat, Antony F. Quinn, Amaia Sangrador-Vegas, Maxim Scheremetjew, Siew-Yit Yong, Rodrigo Lopez, Sarah Hunter Bioinformatics (2014), PMID: 24451626

## License

[The original InterProScan license still applies to this container](https://github.com/ebi-pf-team/interproscan/blob/master/LICENSE)

## Build InterProScan Docker image 

```bash
docker build . -t interproscan:5.65-97.0 && docker tag interproscan:5.65-97.0 interproscan:latest
```

## Using InterProScan

### Download the database

Information to download the database comes from: [https://hub.docker.com/r/interpro/interproscan](https://hub.docker.com/r/interpro/interproscan)
```
# Download data
curl -O http://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.65-97.0/alt/interproscan-data-5.65-97.0.tar.gz

# Check download
curl -O http://ftp.ebi.ac.uk/pub/software/unix/iprscan/5/5.65-97.0/alt/interproscan-data-5.65-97.0.tar.gz.md5
md5sum -c interproscan-data-5.65-97.0.tar.gz.md5

# Extract data
tar -pxzf interproscan-data-5.65-97.0.tar.gz
```

### General use

**Run the application**
```bash
docker run -v /interproscan-5.65-97.0/data:/opt/interproscan/data -v /your/data/dir:/data interproscan:tagname interproscan.sh <options>
```
* *-v /interproscan-5.65-97.0/data* : database used by InterProScan
* *-v /your/data/dir* : directory containing the files that will be analyzed 
* *\<options_\>* : indicate the different options to use

### Example of use

* For help with the different *CD-HIT* options
```bash
docker run interproscan:tagname interproscan.sh

```
* Functional annotation (protein sequences)
```bash
docker run /interproscan-5.65-97.0/data:/opt/interproscan/data -v /your/data/dir:/data -i input.fa -b output
```

## Interactive shell

To run an interactive shell
```bash
docker run -v /interproscan-5.65-97.0/data:/opt/interproscan/data -v /your/data/dir:/data interproscan:tagname interproscan.sh
```
After this command you work in the container. You can directly execute the different CD-HIT commands.

## Push to Docker Hub
1. Rename tool with username
```bash
docker tag interproscan:tagname <user-name>/interproscan:tagname
```
2. Push to Docker Hub
```bash
docker push <user-name>/interproscan:tagname
```

### Retrieve the image from Docker Hub

```bash
docker pull <user-name>/interproscan:tagname
```
