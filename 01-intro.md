---
pagetitle: "SARS-CoV-2 Genomics"
---

# SARS-CoV-2 Genomic Surveillance

:::highlight

**Questions**

- How can genomic surveillance help during a pandemic?
- What protocols and technologies are used for SARS-Cov-2 genome sequencing?
- What factors should be considered when collecting samples for sequencing?
- What are some of the main SARS-CoV-2 data repositories and projects?

**Learning Objectives**

- Enumerate some examples of how the genomic surveillance of SARS-CoV-2 has impacted public health decisions during the ongoing pandemic. 
- Contrast different sequencing protocols (e.g. amplicon, metagenomic) and technologies (e.g. Illumina and Nanopore) commonly used for SARS-CoV-2 sequencing, including the pros and cons of each. 
- Understand the steps involved in the widespread ARTIC protocol and the differences between its versions. 
- List key metadata fields needed with each sample to make best use of the data and recognise some limitations related to privacy.
- Recognise what the main steps are in processing raw sequencing data to generate consensus genome sequences, including sequence alignment, primer trimming and consensus generation. 
- Describe the sources of information that can be obtained from GISAID, Pango, Nextstrain and the WHO nomenclature systems. 
- Describe what a variant of concern (VOC) is and how it differs from a variant of interest (VOI). 

:::


## What is SARS-CoV-2?

SARS-CoV-2 (Severe acute respiratory syndrome coronavirus 2) is a _betacoronavirus_ resposible for the COVID-19 disease and caused a global outbreak leading to an ongoing pandemic. 
The initial spread of this virus started in the city of Wuhan, in China. 
Despite early efforts to contain its spread in China (through several lockdowns in the country), the virus spread to other provinces within China and, eventually, to other countries across the world. 
This led to the World Health Organisation (WHO) declaring a public health emergency on 30 January 2020 and then a pandemic on 11 March 2020. 

SARS-CoV-2 is an RNA virus, composed of single-stranded RNA.
The first **SARS-CoV-2 genome** was [published in January 2020](https://www.nature.com/articles/s41586-020-2012-7) and is approximately 30Kb long. 
It encodes several proteins including the so-called Spike protein (or 'S' for short), which is used by the virus to interact and eventually enter human cells and cause infection. 
This interaction happens by the binding of the S protein to the ACE2 protein receptor found in human cells. 

![Genome structure of SARS-CoV-2. Source: [Rahimi, Mirzazadeh & Tavakolpour 2021](https://doi.org/10.1016/j.ygeno.2020.09.059)](https://ars.els-cdn.com/content/image/1-s2.0-S0888754320308764-gr1_lrg.jpg)

The genome sequence of SARS-CoV-2 has been a huge contributor to our ability to manage current pandemic. Namely:

- It allowed the development of a vaccine to target the S protein.
- It allowed the development of diagnostic tests for positive cases (lateral flow test and PCR-based test).
- It allowed the development of protocols for whole-genome sequencing of the virus from positive human samples. 

This last point is the focus of our workshop, and we will spend some time looking at how to analyse these data. 

<!--
Very brief and general intro to coronavirus biology (see: https://www.nature.com/articles/s41586-021-04188-6)

- genus betacoronavirus
- phylogenetic context in relation to other viruses
- SARS-CoV-2 spike protein (binds to human ACE2); its structure, e.g. receptor binding domain, furin-cleavage site
  - mutations in spike protein might cause immune escape and/or vaccine inefficiency
- current pandemic overview
-->

## Genomic Surveillance

The number of SARS-CoV-2 genomes sequenced is the largest of a pathogen ever done. 
As such, it has enabled us to [**track how the virus evolves and spreads**](https://www.nature.com/articles/s41586-021-04188-6) both at a local and global scale at an unprecendented resolution. 
This allowed the identification of mutations that affect characteristics of the virus, such as its transmissibility or severity of the disease, and testing new strains of the virus to understand whether they are effectively neutralised by current or future vaccines. 

One of the main applications of SARS-CoV-2 sequencing is to infer relationships between the different circulating forms of the virus. 
This is done by comparing these sequences and building **phylogenetic trees** that reflect their sequence similarities. 
From these, it is possible to identify particular clusters of similar sequences that spread faster than expected, and may therefore be associated with mutations that increase the virus' fitness. 

![Example of global phylogeny from the [Nextstrain public server](https://nextstrain.org/ncov/gisaid/global). Colours show clusters of similar sequences. (Screenshot taken Feb 2022)](images/lineages_example.svg)

For example, one of the first mutations identified from these sequencing efforts was A23403G (an adenine was replaced by a guanine in position 23,403 of the genome), which caused an aminoacid substitution in the S protein that increased virus infectivity and transmissibility. 
Since then, many new forms of the virus have been identified as being of particular concern for public health, and have been [classified by the WHO as **Variants of Concern**](https://www.who.int/en/activities/tracking-SARS-CoV-2-variants/). 
These have been named based on letters of the Greek alphabet, and have been a crucial way to inform public health policy and containment measures around the world.

In addition to the WHO variant nomenclature, there are three main projects that have been instrumental in grouping SARS-CoV-2 sequences into similar groups:

- The [GISAID nomenclature](https://www.gisaid.org/) classifies sequences based on key mutations that define particular groups of sequences in the global phylogeny. It also complements its classification by borrowing information from the _Pango_ nomenclature system.
- The [Pango nomenclature](https://www.pango.network/the-pango-nomenclature-system/statement-of-nomenclature-rules/) is based on the phylogeny of SARS-CoV-2 and defined as groups of sequences that share a common ancestor and a distinctive sequence feature (for example, all share the same single nucleotide change). This nomenclature is also sometimes referred as "[Rambaut et al. 2020](https://doi.org/10.1038/s41564-020-0770-5)" after the respective publication.
- The [Nextstrain nomenclature](https://nextstrain.org/blog/2020-06-02-SARSCoV2-clade-naming) is slightly more informal than the above, its main purpose being to facilitate public health discussions. Despite this, it is still informed by the phylogenetic placement of sequences in a tree and therefore has a large overlap with the _Pango_ nomenclature.

We will learn more about how sequences are classified into _lineages_ and _variants of concern_ in the section about [Lineage Assignment](05-lineage_assignment.html).


:::exercise

- Looking through the [WHO variants page](https://www.who.int/en/activities/tracking-SARS-CoV-2-variants/), can you find what the difference is between a _Variant of Interest_ (VOI) and a _Variant of Concern_ (VOC)?
- Can you find the correspondence between the VOCs and their respective lineages in other classification systems (GISAID, Nextstrain and Pango)?
- Go to the [outbreak.info](https://outbreak.info/location-reports) website and search for a country of your choice (for example, your country of origin or where you live). 
- How many sequences are available from the last 360 days? (Note: by default only the last 60 days are shown. You can change this in the text box found on the right of the report page.)
- What were the most common lineages of the virus in circulation in the last 360 days? Do you notice sharp changes in the frequency of WHO _Variants of Concern_?

:::


:::note

**What is the difference: strain, lineage, clade, variant?**

These terms are sometimes used interchangeably in informal conversations about SARS-CoV-2.
For our purposes, these are the definitions we will use:

A **strain** is a group of viruses are sufficiently diverged from others, so that they are quite distinct at a sequence level as well as in their biological properties. SARS-CoV-2 is still considered to be a single strain. Examples of other coronavirus strains are SARS-CoV and MERS-CoV.

The terms **lineage** and **clade** are somewhat similar, in that both represent groups of similar sequences, inferred from a phylogenetic analysis and sharing a common ancestor. 
Their main difference (at least in the current SARS-CoV-2 nomenclature systems) is the level of resolution. 
Clades tend to be more broadly defined and therefore include more sequences within it. 
They are useful to discuss long-term trends during a pandemic.
Lineages have a finer resolution, being useful to identify patterns related to a recent outbreak.

Since a phylogenetic tree is inherently hierarchical, there isn't always a clear-cut way of defining where one lineage/clade starts and another ends. That is why lineage classification is a partially manual process, involving human curation by experts. 

Finally, the term **variant** is usually used to refer to WHO's _variants of interest_ or _variants of concern_ (e.g. the Alpha, Delta and Omicron variants). 
Variants are distinct from each other by the _combination of all sequence changes_ in their genomes.
The term "variant" can be ambiguous when used in the field of bioinformatics, and we return to this in the section about [Lineage Assigment](05-lineage_assignment.md)

:::



## The GISAID Database

The widespread use of genome sequences would have not been possible without the ability to centrally collect these sequences and make them available to researchers and public health professionals. 
The main repository used to deposit SARS-CoV-2 sequences is the database managed by the [GISAID Initiative](https://www.gisaid.org/). 
This allows sharing the sequencing data as well as metadata associated with it (such as dates of collection, geo-location, patient information, etc.).
For example, the [outbreak.info](https://outbreak.info/location-reports) website that we just used in the exercise above directly pulls data from GISAID to update its reports on a daily basis.

At the end of this course you too will be able to contribute to this database, by producing full genome sequences assembled from sequencing data. 

:::note
**Create a GISAID account**

Go to the [GISAID registration page](https://www.gisaid.org/registration/register/) and create an account, so you can gain access to the data stored in GISAID as well as the ability to submit your own sequences in the future. 

:::


## SARS-CoV-2 Sequencing

Routine SARS-CoV-2 sequencing is done with a method generally referred to as _amplicon sequencing_. 
This method relies on amplifying the genetic material using [polymerase chain reaction](https://youtu.be/aUBJtHwHASA) (PCR) with a panel of primers designed against the known SARS-CoV-2 genome. 

One of the most popular methods for preparing virus RNA for sequencing have been developed by the **ARTIC** network, whose aim is to develop standardised protocols for viral sample processing.
One of the key contributions of this network is to provide the community with a panel of primers that tile the whole genome of SARS-CoV-2, which are updated and optimised to work on the most common circulating lineages. 

![Schematic of the ARTIC protocol. Source: [Gohl et al. 2020](https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-020-07283-6/figures/1)](images/artic_protocol.png)

Other methods of sequencing can also be used.
For example, **metagenomic RNA sequencing** was the method used to assemble the [first SARS-CoV-2 genome](https://doi.org/10.1038/s41586-020-2012-7) and one of the [first sequences in Cambodia](https://doi.org/10.1101/2020.03.02.968818). 
This method consists of extracting viral RNA (using commercially available kits) followed by high-throughput RNA-seq. 
The resulting sequences are then compared with nucleotide databases of known organisms, and viral sequences selected for de-novo assembly.

**Sequence capture** protocols are also available, whereby the samples are enriched for the target virus by using a panel of probes against the SARS-CoV-2 genome, followed by sequencing and de-novo assembly. 

Despite these alternative methods, amplicon sequencing remains one of the most popular methods for large-scale viral surveillance due to its low cost and relatively high-throughput nature. 
The data generated from this method will be the focus of this course. 

:::note
**Illumina or Nanopore?**

Both of these sequencing platforms can be used to sequence amplicon samples. 

_Nanopore_ platforms allow sequencing 96 samples at a time, are readily available as portable devices, and have fast run times.
This gives them great flexibility, making them an excellent solution for rapidly building sequencing capacity in a lab. 

By comparison, _Illumina_ platforms give higher throughput, are cheaper to run per sample and have lower error rates. 
However, they require substantial upfront cost to setup and equip in the lab and take longer to run.

:::


## Sample Collection

When collecting patient samples for sequencing, it is important to quantify the viral load in the sample. 
This is usually done by [quantitative RT-PCR (RT-qPCR)](https://dx.doi.org/10.3390%2Fijms21083004), whereby the amplification of the samples is monitored by measuring a dye that is incorporated during the PCR reaction.
This results in amplification curves, which reflect the amount of RNA present in the sample.
The more PCR cycles are needed to saturate the signal, the lower the amount of virus in the sample. 

![Overview of RT-qPCR quantification of viral load in a sample. Adapted from [Smyrlaki et al. 2020](https://doi.org/10.1038/s41467-020-18611-5)](images/virus-RT-qPCR.png)

The result of RT-qPCR is usually expressed as the PCR cycle at which a particular threshold in the amplification curve is reached, the **Ct value**. 
Generally, samples with **Ct > 30** are not worth sequencing, as their genome completeness is likely going to be low due to the low amounts of starting material. 

![Relationship between RT-qPCR Ct value and resulting genome completeness. Source: [Jared Simpson's talk at CLIMB BIG DATA workshop](https://youtu.be/Fb-SID2DlB0)](images/Ct_coverage_relationship.png)


### Metadata

One important consideration when collecting samples, is to record as much information as possible about each sample. 
The Public Health Alliance for Genomic Epidemiology (PHA4GE) coalition provides several [guidelines](https://www.preprints.org/manuscript/202008.0220/v1) and [a protocol](https://dx.doi.org/10.17504/protocols.io.btpznmp6) to aid in metadata collection. 

Two key pieces of information for genomic surveillance are the date of sample collection and the geographic location of that sample. 
This information can be used to understand which variants are circulating in an area at any given time.

Privacy concerns need to be considered when collecting and storing sensitive data.
However, it should be noted that sensitive data can still be collected, even if it is not shared publicly (e.g. via the GISAID database). 
Such sensitive information may still be useful for the relevant public health authorities, who may use those sensitive information for a finer analysis of the data. 
For example, epidemiological analysis will require individual-level metadata ("person, place, time") to be available, in order to track the dynamics of transmission within a community.

:::exercise

Open the folder under "Course_Materials > 01-Unix > metadata", where you will find several CSV files with information about samples that were sequenced and will be analysed by us later in the course. 
Double-click to open one of these files (any of them is fine), which should open them on a spreadsheet software (on our training machines it is LibreOffice, but Excel would also work).

The column names of these files are based on the PHA4GE nomenclature system. 

- Go to the [PHA4GE metadata collection protocol]((https://dx.doi.org/10.17504/protocols.io.btpznmp6)) and read throught the first steps to find the link to the collection templates. 
- From that link, go to the Supporting Materials to find the "field mappings" spreadsheet, which matches naming conventions between PHA4GE and other databases such as GISAID.
- Based on this information, can you match the column names from our sample information table to the fields required by GISAID?
- What do you think is the naming convention for the isolate name? How would you adjust this when uploading the data to GISAID?

<details><summary>Answer</summary>

TODO

</details>

:::


## SARS-CoV-2 Bioinformatics

What bioinformatic skills do we need in order to analyse SARS-CoV-2 genome sequencing data? 
While there are several software tools that have been specifically developed for SARS-CoV-2 analysis (and we will see some of them in this course), there is a set of foundational skills that are applicable to any bioinformatics application:

- The use of the **Unix command line**. Linux is the most common operating system for computational work and most of the bioinformatic software only runs on it. 
- Getting familiar with common **file formats in bioinformatics**. This includes files to store nucleotide sequences, sequence alignments to a reference genome, gene annotations, phylogenetic trees, amongst others. 
- Understand software tools' **documentation** and how to configure different options when running our analyses.

We will turn to these topics in the following sessions. 


## Summary

:::highlight
**Key Points**

- one
- two
- three

:::

