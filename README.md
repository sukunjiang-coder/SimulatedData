# Simulated Multi-Generational Admixed Haplotypes (AFR–EUR–EAS)

## Overview

This dataset contains simulated admixed haplotypes derived from three continental populations

- **AFR** – African (YRI)  
- **EUR** – European (CEU)  
- **EAS** – East Asian (CHS)

Two generational depths are included:

- **G5** – 5 generations of recombination  
- **G10** – 10 generations of recombination  

Each generation contains 5 simulated diploid individuals.  
Both haplotype alleles and ground-truth local ancestry labels are provided.

---

## File Structure

```text
Simulated_Admixed_Data/
├── G5_hap.txt
├── G5_anc.txt
├── G10_hap.txt
└── G10_anc.txt
```

---

## Haplotype Data Format

Sample and reference haplotype files share the same **tab-delimited** format.

### Example

```text
rsID        position    07_48_05_A   07_48_05_B
rs10458597  554484      A           A
rs2185539   556738      C           C
rs11240767  718814      C           C
rs12564807  724325      A           G
```

- Each individual is represented by **two columns**: `_A` and `_B`
- Alleles are encoded as: **A / T / C / G**
- The first two columns are always: `rsID` and `position`

---

## Local Ancestry Truth Format

The ancestry file preserves variant positions and replaces nucleotide alleles with inferred ancestry labels.

### Example

```text
rsID        position    07_48_05_A   07_48_05_B
rs10458597  554484      1           2
rs2185539   556738      1           2
rs11240767  718814      1           2
rs12564807  724325      1           3
```

### Ancestry Encoding

- **1 = AFR**
- **2 = EUR**
- **3 = EAS**

Numeric codes correspond to reference populations defined in the configuration file.

---

## Simulation Summary

- Founder haplotypes were randomly selected from AFR (YRI), EUR (CEU), and EAS (CHS).
- Cross-population mating was simulated.
- Recombination events were introduced during meiosis.
- No mutation was introduced.
- Sample IDs are anonymized.
- No raw individual-level data are redistributed.

### Generational Design

- **Generation 5 (G5):** Moderate recombination; ancestry blocks remain relatively long.
- **Generation 10 (G10):** Increased recombination; ancestry blocks are shorter and more fragmented.

This dataset is intended for benchmarking local ancestry inference and ancestry-aware phasing methods under different admixture depths.
