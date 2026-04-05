# VGP Genome Assembly Pipeline
 
**Platform:** Galaxy (usegalaxy.org)  
**Tutorial:** [VGP Genome Assembly — Galaxy Training Network](https://training.galaxyproject.org/training-material/topics/assembly/tutorials/vgp_genome_assembly/tutorial.html)

---

## Project Overview

This repository documents the complete execution of the Vertebrate 
Genomes Project (VGP) genome assembly pipeline using the Galaxy 
bioinformatics platform.

The pipeline combines three sequencing technologies:
- **PacBio HiFi reads** — long accurate reads for contig assembly
- **Bionano optical maps** — ultra-long physical maps for scaffolding
- **Illumina Hi-C reads** — chromatin data for chromosome-scale scaffolding

---

## Pipeline Overview
```
HiFi reads → Cutadapt → Meryl → GenomeScope2
                                      ↓
HiFi + Hi-C → hifiasm → gfastats → BUSCO + Merqury
                                      ↓
                    Bionano scaffolding
                                      ↓
                    Hi-C scaffolding (YaHS)
                                      ↓
                  Chromosome-level assembly
```

---

## Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| Cutadapt | 4.4 | Remove HiFi adapters |
| Meryl | 1.3 | K-mer counting |
| GenomeScope2 | 2.0 | Genome size estimation |
| hifiasm | 0.19.8 | Genome assembly |
| gfastats | 1.3.6 | Assembly statistics |
| BUSCO | 5.5.0 | Completeness assessment |
| Merqury | 1.3 | Quality assessment |
| Bionano Hybrid Scaffold | 3.7.0 | Optical map scaffolding |
| BWA-MEM2 | 2.2.1 | Hi-C read mapping |
| YaHS | 1.2a.2 | Hi-C scaffolding |
| PretextMap + Snapshot | 0.1.9 | Contact map visualization |

---

## Key Results

| Metric | Value |
|--------|-------|
| Estimated genome size | ~11.7 Mb |
| Final scaffolds | ~16 (chromosome-level) |
| BUSCO completeness | [your value]% |
| QV score | [your value] |

---

## Repository Structure
```
vgp-genome-assembly/
├── README.md
├── steps/
│   ├── 00_galaxy_setup.md
│   ├── 01_cutadapt_meryl.md
│   ├── 02_genomescope_hifiasm_gfastats.md
│   └── 03_busco_merqury_bionano_hic.md
├── results/
│   └── results.md
└── images/
    └── (all screenshots)
```

---

## References

1. Rhie et al. (2021). Towards complete and error-free genome assemblies. *Nature*
2. Cheng et al. (2021). Haplotype-resolved assembly with hifiasm. *Nature Methods*
3. Zhou et al. (2022). YaHS: yet another Hi-C scaffolding tool. *Bioinformatics*
