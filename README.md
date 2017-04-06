# mappet - mapped alignment excision tool (gene-cutter on steroids)

Extract from a set of reads their mapping on a template sequence. 

Homed at <https://github.com/zwets/mappet>.


## Background

Mappet is the better [gene-cutter](https://github.com/zwets/blast-galley).

I wrote gene-cutter to solve the simple problem of excising a gene (or any
region matching a template) from a nucleotide sequence, using only BLAST.
Gene-cutter has the downside that it misses matches that straddle contigs.
This could be solved by lowering the coverage threshold and stitching
"overlap matches" together, but the more general solution is to use mapping.
This is what `mappet` does.


## Usage

Mappet is self-contained.  Use `mappet --help`.

**Tip:** by default, `mappet` outputs only the resulting consensus FASTA
sequence.  Use option `--keep` to retain the intermediate SAM and VCF files.


## Requirements

`mappet` requires `bwa`, `samtools`, `bcftools`, `fastq_to_fasta`, and
`fastq-unbreak` to be on the PATH, and `vcfutils.pl` to be in
`/usr/share/samtools` (this is where it is on Ubuntu).

On Ubuntu (16.04) these executables can be obtained by:

```bash
# Install distro packages with all tools except fastq-unbreak
sudo apt-get install bwa samtools fastx-toolkit

# Install fastq-unbreak
sudo apt-get install build-essential git # for make and c++ compiler
git clone 'https://github.com/zwets/fastq-utils.git'
cd fastq-utils
make fastq-unbreak
cp fastq-unbreak $HOME/bin  # Assuming you have ~/bin on your path
```

