---
layout: page
title: Data Access
permalink: /data/
order: 10
---
## IGSR - 1000 Genomes Sample Data

The International Genome Sample Resource (IGSR) presents all the data it has on the 1000 Genomes samples through the [1000 Genomes FTP site]({{site.ebi_ftp}}){:target="_blank"} and the [mirror site]({{site.ncbi_ftp}}){:target="_blank"} hosted at the NCBI. Currently this FTP site contains the three main releases of the 1000 Genomes Project. 

<table class='table table-striped'>
  <thead>
    <tr>
      <th>1000 Genomes Release</th>
      <th>Variants</th>
      <th>Individuals</th>
      <th>Populations</th>
      <th>VCF</th>
      <th>Sequence and Alignments</th>
      <th>Supporting Data</th>
    </tr>
  </thead>
  <tbody>
    {% for release in site.data.phasedata %}
    <tr>
      <td>{{release.release}}</td>
      <td>{{release.variants}}</td>
      <td>{{release.individuals}}</td>
      <td>{{release.populations}}</td>
      <td><a href='{{release.vcf}}' target="_blank">VCF</a></td>
      <td><a href='{{release.seq}}' target="_blank">Alignments</a></td>
      <td>{% if release.supporting %}<a href='{{release.supporting}}' target="_blank">Supporting Data</a>{% else %} - {% endif %}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

##1000 Genomes Data Access Tools

The [FTP site](ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/){:target="_blank"} is accessible both over FTP and [HTTP]({{site.ebi_ftp| replace:'ftp://', 'http://'}}){:target="_blank"}. It is also accessible via two fast download tools, aspera and globus grid ftp.

###Aspera

The data is also via an Aspera server from both sites. To be able to use this service you need to download the [Aspera connect software](http://asperasoft.com/software/transfer-clients/connect-web-browser-plug-in/). This provides both a browser plug in for downloading data and a bulk download client called ascp. An example command line to get a file using ascp looks like:

{% highlight bash %}
ascp -i bin/aspera/etc/asperaweb_id_dsa.putty -Tr -Q -l 100M \
-L- fasp-g1k@fasp.1000genomes.ebi.ac.uk:vol1/ftp/release/20100804/ALL.2of4intersection.20100804.genotypes.vcf.gz ./
{% endhighlight %}

The location of ``-i`` will depend on where the ascp program was installed. This key should not ask you for a password. IGSR data is freely available and should never request a password for download.

###Globus Grid FTP

The 1000 Genomes FTP site is available as an end point in the [Globus Online system](https://www.globus.org/){:target="_blank"}. In order to access the data you need to sign up for an account with Globus via their [signup page](https://www.globus.org/SignUp){:target="_blank"}. You must also install the [Globus Connect Personal software](https://support.globus.org/entries/24044351){:target="_blank"} and setup a personal endpoint to download the data too.

The 1000 Genomes end point is one of several EMBL-EBI hosted end points and is called ``ebi#1000genomes``. When you have setup your personal end point you should be able to start a transfer using their web front end.

![Globus screenshot]({{ '/images/globus_1000genomes.png' | prepend: site.baseurl }}){:class="center-block"}

The Globus website has support for [setting up accounts](https://support.globus.org/entries/23583857-Sign-Up-and-Transfer-Files-with-Globus-Online){:target="_blank"} and [installing the globus personal connect software](https://support.globus.org/forums/22130516-Globus-Connect-Personal){:target="_blank"}.