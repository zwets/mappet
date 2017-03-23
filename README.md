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

