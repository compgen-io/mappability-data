# Genome mappability

Mappability was calculated for a variety of sizes for the reference human genome (GRCh38p14). The
mappability scores are available as a tabix-indexed BedGraph file with a score for each position in the genome.
There is one file for each chromosome for size considerations.

## Method

For each chromosome, the genome was exhaustively split into N-mer length fragments. This means that each position will (on average) be covered by N fragments. Each fragment was aligned back to the genome using `bwa mem`. The mappability of the fragment was calculated as `1/number_of_top_hits`. So, if a fragment perfectly aligned to the genome in 4 locations, the score would be 0.25. The mappability of specific location was then calculated as the average score across all fragments that overlap that position.

The workflow scripts and more details on the process are available here: https://github.com/compgen-io/mappability

## Data

GRCh38

| name | species | desc | fragment length | data |
|------|---------|------|-----------------|-|
| hg38M\_35 | Human | GRCh38 - XY | 35 bp | https://github.com/compgen-io/mappability-data/releases/tag/hg38M_35 |

