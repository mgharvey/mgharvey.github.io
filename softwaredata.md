---
layout: page
permalink: /softwaredata/
title: Software/Data
tagline: Michael G. Harvey
tags: [about, research, Michael G. Harvey]
modified: 5-20-14
comments: true
image:
  feature: tapajos.jpg
---

***

I try to make all my data and software freely available and easily accessible. Scripts are generally available from Github, and data from Dryad or elsewhere. If you notice something I've neglected to post, please <a href="mailto:mharve9@lsu.edu" target="_blank">contact me</a>.

# <a href="https://github.com/mgharvey/mps-sim" target="_blank">mps-sim</a>

A program for simulating large sets of alignments resembling those obtained from massively parallel sequencing approaches like RAD-Seq and sequence capture of ultraconserved elements.

# <a href="https://github.com/mgharvey/misc_python" target="_blank">misc_python</a>

Miscellaneous Python code, mostly for processing and manipulating genetic data. Many of these are scripts for formatting input files for different phylogenetic and population genetics programs. Included are scripts for:

* Formatting input files for Treemix (Pickrell and Pritchard 2012) and bootstrapping Treemix trees. See blog post.

* Formatting input files for BUCKy (Larget ) and running MrBayes () and mbsum iteratively on many loci

* Formatting input files for dadi and also some example scripts for demographic models, running dadi, obtaining summary statistics, reformatting output, etc.

* Detecting missing taxa in alignments (in a directory with many alignments) and adding in missing data for those taxa.

* Splitting hapolotypes with ambiguity codes at heterozygous sites into diplotypes.

# <a href="https://github.com/mgharvey/misc_R" target="_blank">misc_R</a>

Miscellaneous R code, mostly for analyzing and visualizing data, including scripts for:

* Visualizing rough distributions of gene trees in "cloudograms"

* UCE alignments from 48 Neoavian birds (McCormack et al. 2013)

* UCE alignments from multiple individuals within 5 Neotropical birds (Smith et al. 2014)

* RAD-Seq data from 72 individuals of *Xenops minutus*