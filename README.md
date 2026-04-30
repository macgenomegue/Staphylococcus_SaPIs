Staphylococcus SaPIs Database

Overview

This repository contains a curated FASTA database of Staphylococcal Pathogenicity Islands (SaPIs) for use in genomic screening of Staphylococcus aureus and related species.

SaPIs are mobile genetic elements that frequently carry virulence determinants, including enterotoxin genes. Their detection is critical for risk characterisation of enterotoxigenic strains in food safety and public health contexts.

Contents
Staphylococcus_SaPIs.fasta: curated nucleotide sequences of SaPIs

Intended Use

This database is designed for:
- Whole genome sequencing (WGS) analysis
- Screening using BLAST+ or ABRicate
- Detection of SaPI-associated virulence regions

Recommended Tools
- BLAST+ (blastn)
- ABRicate

Recommended Parameters
- Minimum identity: 80 percent
- Minimum coverage: 95 percent

These thresholds balance sensitivity and specificity for detection of SaPI regions across diverse Staphylococcus genomes.

Example Usage

BLAST+
makeblastdb -in Staphylococcus_SaPIs.fasta -dbtype nucl -out SaPIs_db
blastn -query genome.fasta \

-db SaPIs_db \
-out results.txt \
-outfmt "6 qseqid sseqid pident length qcovs evalue bitscore" \
-perc_identity 80

Filter results for coverage >=95 percent.

ABRicate
abricate --db Staphylococcus_SaPIs genome.fasta > report.tab

Ensure database is installed in ABRicate database directory.

Interpretation
Detection of SaPI sequences indicates the presence of mobile genetic elements associated with virulence. This includes potential carriage of enterotoxin genes. Detection does not confirm gene expression or toxin production.

Limitations
- Database is limited to currently curated sequences
- Novel or highly divergent SaPIs may not be detected
- Results depend on assembly quality and completeness

Curation

Sequences were compiled from public databases and literature. Details of inclusion criteria and sources should be documented if expanded.

Versioning

Version: 1.0
Date: 2026-04-30

Citation

If you use this database, cite:
Staphylococcus SaPIs Database. GitHub repository. Available at: https://github.com/macgenomegue/Staphylococcus_SaPIs

Suggested citation format
Staphylococcus SaPIs Database (version 1.0). Available at: https://github.com/macgenomegue/Staphylococcus_SaPIs
Macori G, Bellio A, Bianchi DM, Chiesa F, Gallina S, Romano A, Zuccon F, Cabrera-Rubio R, Cauquil A, Merda D, Auvray F. Genome-wide profiling of enterotoxigenic Staphylococcus aureus strains used for the production of naturally contaminated cheeses. Genes. 2019 Dec 27;11(1):33.
Contact

Maintainer: [Guerrino Macori]
Institution: [University College Dublin]

License
This database is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).
Full licence text: https://creativecommons.org/licenses/by/4.0/
