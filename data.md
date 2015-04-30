---
layout: page
title: Data Access
permalink: /data/
order: 10
---
#IGSR - 1000 Genomes Sample Data

The International Genome Sample Resource (IGSR) presents all the data it has on the 1000 Genomes samples through the [1000 Genomes FTP site](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/) and the [mirror site](ftp://ftp-trace.ncbi.nih.gov/1000genomes/ftp/) hosted at the NCBI

Currently this FTP site contains the three main releases of the 1000 Genomes Project. 

##1000 Genomes Phase 3 release

The Phase 3 release contains more than 84 million variants and genotypes for 2504 individuals from 26 different populations. These files are presenting in VCF format in the [20130502 release directory](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/release/20130502/)

The sequence and alignment data which support these results can be found under [ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/phase3](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/phase3). 

Functional annotation, genotypes for related samples, per sample depth cover and other affiliated resources can be found in the [supporting directory](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/release/20130502/supporting/)

##1000 Genomes Phase 1 release

##1000 Genomes Pilot Release

##1000 Genomes Data Access Tools

The [FTP site](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/) is accessible over [FTP](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/) and [HTTP](http://ftp.1000genomes.ebi.ac.uk/vol1/ftp/). It is also accessible via two fast download tools, aspera and globus grid ftp.

###Aspera

The data is also via an Aspera server from both sites. To be able to use this service you need to download the [Aspera connect software](http://asperasoft.com/software/transfer-clients/connect-web-browser-plug-in/). This provides both a browser plug in for downloading data and a bulk download client called ascp. An example command line to get a file using ascp looks like:

```
ascp -i bin/aspera/etc/asperaweb_id_dsa.putty -Tr -Q -l 100M -L- fasp-g1k@fasp.1000genomes.ebi.ac.uk:vol1/ftp/release/20100804/ALL.2of4intersection.20100804.genotypes.vcf.gz ./
```
The location of -i will depend on where the ascp program was installed.

This password should not ask you for a password. All the IGSR data is freely available and should not ever request a password for download.

###Globus Grid FTP

The 1000 Genomes FTP site is available as an end point in the [Globus Online system](https://www.globus.org/). In order to access the data you need to sign up for an account with Globus via their [signup page](https://www.globus.org/SignUp). You must also install the [Globus Connect Personal software](https://support.globus.org/entries/24044351) and setup a personal endpoint to download the data too.

The 1000 Genomes end point is one of several EMBL-EBI hosted end points and is called ebi#1000genomes

When you have setup your personal end point you should be able to start a transfer using their web front end.

![Globus screenshot](http://www.1000genomes.org/sites/1000genomes.org/files/documents/globus_1000genomes.png)

The Globus website has support for [setting up accounts](https://support.globus.org/entries/23583857-Sign-Up-and-Transfer-Files-with-Globus-Online), and [installing the globus personal connect software](https://support.globus.org/forums/22130516-Globus-Connect-Personal)