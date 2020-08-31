# QBB2020 - Day 1 - Evening Exercise

For this assignment we will be working with a [.SAM file](https://samtools.github.io/hts-specs/SAMv1.pdf). We would normally use `samtools` to generate the file. Instead, you'll need to download it.

```
wget  https://bx.bio.jhu.edu/track-hubs/cmdb/c
```

**Please make sure not to add, commit, or push this `.sam` file to GitHub**

While downloading, familiarize yourself with its [format](https://samtools.github.io/hts-specs/SAMv1.pdf).

**TIP:** You may find it very helpful to view this file *on the command line* (not in a Jupyter Python notebook!) using `less -S`:

```
less -S SRR072893.sam
```

Press the `Q` key to quit from this view.

<!-- ```shell
/Users/cmdb/qbb2020-answers/day1-evening/ $ samtools view /Users/cmdb/data/results/SRR072893.bam > SRR072893.sam
``` -->

It may also be helpful to debug your code using a small subset of reads so things run faster. You can create this using the `head` command in bash.

```shell
head -n 1000 SRR072893.sam > debug.sam
```

For each question, submit a Jupyter notebook file that contains your Python code and your output. Suggested name: `day1-evening-#.ipynb`.

**Basic Exercises**

1. Count number of alignments
2. Count number of alignments that match perfectly to the genome
    - HINT: This is encoded in one of the sam format's [optional fields](https://samtools.github.io/hts-specs/SAMtags.pdf).
3. For the first 10 alignments, print just the column indicating which chromosome a given read aligns to
    - HINT: `.split()`
4. Calculate average MAPQ score across all reads
    - HINT: think about string and numeric type conversions
5. Count number of reads that start their alignment on chromosome 2L between base 10000 and 20000 (inclusive)

**Advanced Exercises**

1. How many reads map to the reverse strand?
    - HINT 1: sam flag 0x10 bit
    - HINT 2: stackoverflow.com/questions/2591483/getting-a-specific-bit-value-in-a-byte-string
2. Determine how many reads have an average quality score >30
    - HINT 1: fastq wiki phred+33
    - HINT 2: stackoverflow.com/questions/227459/ascii-value-of-a-character-in-python
3. Count the number of indels of length 1, 2, 3, 4, greater than 4
    - HINT: This is encoded in the "CIGAR" field
