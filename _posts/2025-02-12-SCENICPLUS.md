---
layout: post
title: SCENIC+ Tutorial
date: 2025-02-12 04:00:00
description: Note and sample questions from ECE 271A
tags: bioinformatics pipeline tutorial
categories: bioinformatics
---

## Download 10X output

```{bash}
#!/bin/bash

samples=("s1" "s2")
# Base URL for download
base_url="https://XXX/counts"

# Directory paths

download_dir="/volume/data/XXX/raw"

for sample in "${samples[@]}"
do
    echo "Processing sample: $sample"

    # Create a directory for the sample
    mkdir -p "$download_dir/$sample"
    
    # Download the folder contents
"$download_dir" "$base_url/$sample/outs/"

    wget -r -nc -np -nH --cut-dirs=6 -P "$download_dir/$sample" "$base_url/$sample/outs/filtered_feature_bc_matrix.h5"
    wget -r -nc -np -nH --cut-dirs=6 -P "$download_dir/$sample" "$base_url/$sample/outs/atac_fragments.tsv.gz"
    wget -r -nc -np -nH --cut-dirs=6 -P "$download_dir/$sample" "$base_url/$sample/outs/atac_fragments.tsv.gz.tbi"
    
    echo "Finished downloading $sample"
done

```

## Scanpy Preprocessing



## Get pycisTopic Object


## Set-up and Run SCENIC+




