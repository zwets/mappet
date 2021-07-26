# mappet - mapped alignment excision tool (gene-cutter on steroids)

Extract from a set of reads their mapping on a template sequence.

Homed at <https://github.com/zwets/mappet>.


## Background

Mappet is [gene-cutter](https://github.com/zwets/blast-galley) for reads.

I wrote gene-cutter to solve the simple problem of excising a gene (or any
region matching a template) from a nucleotide sequence, using only BLAST.
Gene-cutter has the downside that it misses matches that straddle contigs.
That could be solved by lowering the coverage threshold and stitching
"overlap matches" together, but the more general solution is to use mapping.
This is what `mappet` does.


## Usage

Mappet is self-contained.  Use `mappet --help`.

**Tip:** by default, `mappet` outputs only the resulting consensus FASTA
sequence.  Use option `--keep` to retain the intermediate SAM and VCF files.


## Requirements

`mappet` requires `zgrep`, `bwa`, `samtools`, `bcftools` on the PATH, and
will check that these are available.

On Ubuntu these executables can be installed the usual way:

    sudo apt-get install bwa samtools bcftools gzip

