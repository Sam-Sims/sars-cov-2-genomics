---
pagetitle: "SARS-CoV-2 Genomics"
---

# Introduction to SARS-CoV-2 Genomics

:::highlight

This course will teach you how to analyse sequencing data from SARS-CoV-2 amplicon samples to generate consensus sequences ready to be uploaded to public databases such as GISAID and to be used in other downstream analysis such as variant annotation and phylogeny. We will teach the use of a standardised analysis pipeline (following the widely used ARTIC protocol), which can work with both Illumina and Nanopore data. We will also cover how to assign sequences to lineages, identify variants of interest/concern and produce visualisations to communicate your findings. Along the way, you will gain foundational bioinformatic skills, including the use of the Unix command line and learn to write simple scripts to ensure your analysis is reproducible. 

:::

**Learning Goals:**

- Recognise the uses of genomic surveillance to inform public health actions during a pandemic. 
- Assemble high-quality SARS-CoV-2 genome sequences from raw sequencing data.
- Assign consensus sequences to lineages and identify variants of interest/concern.
- Capture high-quality metadata, recognising its impact on downstream analyses.
- Construct phylogenetic trees to contextualise new samples in a set of background samples.
- Produce visualisations to communicate these findings and help inform public health action. 

**Learning Objectives:**

By the end of this course, learners should be able to:

- Enumerate examples of how the genomic surveillance of SARS-CoV-2 has impacted public health decisions during the ongoing pandemic. 
- Contrast the different technologies and protocols commonly used for SARS-CoV-2 sequencing, including the pros and cons of each. 
- Understand the importance and uses of metadata such as geolocation, date of collection and protocols used. 
- Use the Unix command line to navigate a filesystem, manipulate files, launch programs and write scripts for reproducible analysis.
- Recognise the structure of common sequence file formats in bioinformatics and run basic quality control tools on them.
- Summarise the steps in the bioinformatic pipeline used for assembling SARS-CoV-2 genomes from high-throughput amplicon sequencing.
- Apply the `connor-lab/ncov2019-artic-nf` _Nextflow_ pipeline to generate a consensus sequence from Illumina and Nanopore data.
- Assess the quality of the consensus sequences and identify high-quality sequences suitable for downstream analyses and submission to public databases.
- Assign sequences to lineages and variants using `pangolin` and `nextclade`.
- Interactively explore data and produce visualisations using _Nextstrain_ tools.
- Produce basic phylogenetic trees using _FastTree_ and place sequences in the global phylogeny using _Usher_.
- Manage and install bioinformatics software using _Conda_ and set up _Nextflow_ pipelines from scratch.


## Target Audience

This course is aimed at life scientists interested in the bioinformatic analysis of SARS-CoV-2 genomic data. 
In particular it will benefit those working in SARS-CoV-2 sequencing facilities, such as public health authority labs. 
Those with prior experience in bioinformatics may also benefit from the later sessions of the course, which cover specific tools for SARS-CoV-2 (earlier sessions of the course cover basic skills such as the Unix command line and could be skipped by experienced bioinformaticians).


## Prerequisites

We assume no prior bioinformatics experience or experience with the tools introduced in this course. 
An elementary knowledge of molecular and viral biology is assumed (concepts such as: DNA, RNA, PCR, primers, SNPs).


## Schedule 

:::warning
This is a rough working draft to run across half-day sessions (3-4h long).
Only after the first run will we have a more concrete idea of timings.
:::

| | Session | Duration (estimate) |
|--:|:--|:--|
| Day 1 | [Introduction to SARS-CoV-2 Genomics](01-intro.html) | 1h |
|       | [Introduction to the Unix Command Line](02-unix.html) | 3h |
| Day 2 | [Introduction to NGS Sequencing](03-intro_ngs.html) | 2h |
|       | [SARS-CoV-2 Reference-based Consensus Assembly](04-artic_nextflow.html) | 2h |
| Day 3 | [Lineage Assignment and Variant Classification](05-lineage_assignment.html) | 2h |
|       | [Building phylogenetic trees](06-phylogeny.html) | 2h |
| Day 4 | [Managing and Installing Software](07-nextflow_conda_setup.html) | 2h |
|       | Q&A | 1h |


## Acknowledgements

These materials have been developed as a collaboration between the [Bioinformatics Training Facility](https://bioinfotraining.bio.cam.ac.uk/) at the University of Cambridge and the [New Variant Assessment Platform (NVAP)](https://www.gov.uk/guidance/new-variant-assessment-platform) from Public Health England.
Our partners also include [COG Train](https://www.cogconsortium.uk/cog-train/about-cog-train/).

We thank CLIMB BIG DATA for publicly sharing their [workshop videos](https://www.youtube.com/channel/UCdiGIIyryQL3x-Og5uiY1rw), which inspired some of these materials.
