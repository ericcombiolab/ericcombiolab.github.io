---
layout: post
date: 2024-05-31 16:11:00-0400
inline: false
related_posts: false
title: Deepurify got accepted by Nature Machine Intelligence!
---

Deepurify got accepted by Nature Machine Intelligence!

---

#### Abstract

Metagenome-assembled genomes (MAGs) offer valuable insights into the exploration of microbial dark matter using metagenomic sequencing data. However, there is growing concern that contamination in MAGs may substantially affect the results of downstream analysis. Current MAG decontamination tools primarily rely on marker genes and do not fully use the contextual information of genomic sequences. To overcome this limitation, we introduce Deepurify for MAG decontamination. Deepurify uses a multi-modal deep language model with contrastive learning to match microbial genomic sequences with their taxonomic lineages. It allocates contigs within a MAG to a MAG-separated tree and applies a tree traversal algorithm to partition MAGs into sub-MAGs, with the goal of maximizing the number of high- and medium-quality sub-MAGs. Here we show that Deepurify outperformed MDMclearer and MAGpurify on simulated data, CAMI datasets and real-world datasets with varying complexities. Deepurify increased the number of high-quality MAGs by 20.0% in soil, 45.1% in ocean, 45.5% in plants, 33.8% in freshwater and 28.5% in human faecal metagenomic sequencing datasets.

#### Code

<a href="https://github.com/ericcombiolab/Deepurify/">https://github.com/ericcombiolab/Deepurify/ </a>