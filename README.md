# Clustering

I developed a program that implements a Girvan-Newman natural networking algorithm to cluster nucleotide sequences based on similarity. The program only requires a fasta file as input, and outputs an all-v-all alignment tsv file and fasta file containing clustered sequences with annotated family numbers. It is especially useful for identifying families of transposable elements.

## Dependencies

The user has the option of using either BLAST or minimap2 for all by all comparisons. Make sure the one you choose to use is an executable in your PATH.

#### BLAST

Install BLAST from https://blast.ncbi.nlm.nih.gov/Blast.cgi?CMD=Web&PAGE_TYPE=BlastDocs&DOC_TYPE=Download

#### minimap2

Install minimap2 from https://github.com/lh3/minimap2

## Usage

Make sure that cluster_sequences.py and sequenceAnalyzer.py are in the same directory.

```
python3 cluster_sequences.py [options] -fasta [Path to input fasta file] -algorithm [either "BLAST" or "minimap2"] 
```

### Input

fasta file containing input sequences

### Options

**-min_aln_proportion *f***: Minimum alignment proportion (Default = 0.8)

**-min_cluster_size *I***: Minimum number of sequences required in a particular cluster (Default = 2)

**-min_percentID *I***: Minimum percent identity for all v all BLAST (Default = 80)

### Output

**clusters.fa**: Fasta file containing clustered sequences with annototated family numbers

**final_allvall.tsv**: TSV file containing all by all output from either BLAST or minimap2

minimap2 output format is described here: https://lh3.github.io/minimap2/minimap2.html#2

BLAST output format is described here: https://sites.google.com/site/wiki4metagenomics/tools/blast/blastn-output-format-6


