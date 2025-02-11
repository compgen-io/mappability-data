# Genome mappability

Mappability was calculated for a variety of sizes for the reference human genome (GRCh38p14). The
mappability scores are available as a tabix-indexed BedGraph file with a score for each position in the genome.
There is one file for each chromosome for size considerations.

## Method

For each chromosome, the genome was exhaustively split into N-mer length fragments. This means that each position will (on average) be covered by N fragments. Each fragment was aligned back to the genome using `bwa mem`. The mappability of the fragment was calculated as `1/matches`. So, if a fragment perfectly aligned to the genome in 4 locations, the score would be 0.25. The mappability of specific location was then calculated as the average score across all fragments that overlap that position.

The workflow scripts and more details on the process are available here: https://github.com/compgen-io/mappability

## Data

GRCh38

| species | description | fragment length | data |
|---------|-------------|-----------------|------|
| Human | GRCh38 - XY | 35 bp | [hg38M_35](https://github.com/compgen-io/mappability-data/releases/tag/hg38M_35) |
| Human | GRCh38 - XY | 50 bp | [hg38M_50](https://github.com/compgen-io/mappability-data/releases/tag/hg38M_50) |
| Human | GRCh38 - XY | 100 bp | [hg38M_100](https://github.com/compgen-io/mappability-data/releases/tag/hg38M_100) |
| Human | GRCh38 - XY | 150 bp | [hg38M_150](https://github.com/compgen-io/mappability-data/releases/tag/hg38M_150) |
