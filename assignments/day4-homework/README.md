# QBB2020 - Day 4 - Evening Exercise

## Heuristic sequence alignment

The first step in alignment algorithms like BLAST and FASTA is to find
candidate alignment "seeds" using a dictionary-like index. Here we will
implement the two first steps of such a matcher.

### Data

Use [**this file**](https://github.com/bxlab/qbb2020/raw/master/assignments/day4-homework/droYak2_seq.fa) as your **query** sequence. You can download it directly to your current directory like this:

```Bash
$ wget "https://github.com/bxlab/qbb2020/raw/master/assignments/day4-homework/droYak2_seq.fa"
```

Use `subset.fa` from this afternoon as your **target** sequence

<!--If your `fasta_parser.py` is broken, you can grab ours from here:

```Bash
$ wget "https://raw.githubusercontent.com/qbb2020/raw/master/assignments/day4-homework/fasta_iterator_class.py"
```-->

### Basic Exercise: Extend k-mer counter to k-mer matcher

Implement a script that finds matching _k_-mers between a single query
sequence and a database of targets. The matcher should take three
arguments:

```kmer_matcher.py <target.fa> <query.fa> <k>```

Where `target.fa` is the database, potentially multiple sequences,
`query.fa` is the sequence to align (assume just one sequnce), and
`k` is the _k_-mer size (an integer).

The script should find _k_-mer matches and for each write:

```
target_sequence_name    target_start    query_start k-mer
```

**For submission**: Run the program for `k=11` and submit the first 1000 lines, along with your script.

### Advanced Exercise: Extend matches

Based on your kmer matcher, create `kmer_match_extender.py` which for each
matched _k_-mer will extend on either end to find the longest exact match.
For each target sequence, print the matches ordered from longest to
shortest.

## Hint

You can consider each query _k_-mer (position in the query) independently and in order.
