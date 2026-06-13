# Sanger Sequencing Chromatogram Interpretation: A Complete Visual Guide

A comprehensive visual study guide dedicated to the interpretation of Sanger sequencing chromatograms. This repository provides diagnostic patterns and schematic traces to help researchers, medical laboratory professionals, and bioinformaticians distinguish real biological variants (SNPs, Indels) from technical sequencing noise.

[**View the Interactive Guide**](https://shamihsnn.github.io/Sanger-Sequencing-common-errors-/)

## Table of Contents
- [Overview](#overview)
- [Diagnostic Patterns & Artifacts](#diagnostic-patterns--artifacts)
- [Quality Metrics (Phred Scores)](#quality-metrics-phred-scores)
- [Template & Primer Best Practices](#template--primer-best-practices)
- [Interpretation Rules](#interpretation-rules)

## Overview

Accurate sequence analysis requires reading the trace, not just the text output. A clean reference standard chromatogram exhibits **one dominant, sharp peak per base position** with a flat baseline between peaks. 

* The most reliable region of a read is typically between bases ~50–600.
* The first 20–40 bases often contain noise from unincorporated primers.
* Signal quality naturally degrades toward the end of the run due to reagent depletion.

## Diagnostic Patterns & Artifacts

This guide covers 12 distinct chromatogram patterns encountered during DNA sequencing analysis. Key troubleshooting profiles include:

* **Heterozygous SNP vs. Mixed Template:** Differentiating a true 1:1 double peak at a specific locus from systemic contamination.
* **Homozygous Variants:** Identifying mutations that appear visually clean but mismatch against the reference sequence.
* **Indel (Heterozygous):** Detecting sudden permanent phase shifts requiring TIDE/ICE tool analysis.
* **Technical Artifacts:** Troubleshooting Dye Blobs, Broad Peaks, Signal Saturation (spectral pull-up), and Stutter Peaks caused by polymerase slippage.

## Quality Metrics (Phred Scores)

Base-call confidence is quantified using Phred quality scores ($Q = -10 \times \log_{10}(P)$). 
* **Q20 (99% Accuracy):** The minimum acceptable quality threshold for downstream application (1 in 100 error rate).
* **Q30 (99.9% Accuracy):** High-quality benchmark for sequencing standards.
* Bases falling below Q20 should be trimmed prior to variant calling.

## Template & Primer Best Practices

To avoid common chromatogram errors, adhere to strict template preparation protocols:

### Template Quality
* **Plasmid DNA:** 150–300 ng/reaction.
* **PCR Products:** 10–40 ng/reaction.
* **Purity Ratios:** A260/A280 between 1.8–2.0; A260/A230 $\ge$ 2.0.
* Ensure removal of EDTA, excess salts, and residual ethanol.

### Primer Design
* **Length:** 18–24 nucleotides.
* **GC Content:** 40–60%.
* **Positioning:** Prime $\ge$ 100 bp away from the primary region of interest to bypass early read noise.

## Interpretation Rules

1. **Verify Bidirectionally:** Never rely on a single forward trace. Confirm all suspected variants with a reverse read.
2. **Align to Reference:** Homozygous changes are strictly invisible without a reference alignment.
3. **Trim Low-Quality Ends:** Do not interpret base calls from the decaying tail end of a chromatogram.

---
*Note: This repository synthesizes information from established sequencing core facilities (e.g., MGH DNA Core, Harvard Biopolymers Facility). Always consult your specific instrument protocols.*
