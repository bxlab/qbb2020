# QBB2020 - Day 3 - Homework Exercises

## Instructions

Prepare your workspace, practice software installation, and summarize genome annotations.
`git commit` and `git push` the results of each exercise after completion (please do not wait till the end). See the notes at the end of each exercise to see which file(s) you should commit.  
Scroll to the end for cheat sheets, tutorials, etc.

## Exercises

0. Make sure your `day3` conda environment is active during these exercises.  Your prompt should look like:

    ```
    (day3) [~]
    ```

1. Prepare your workspace:

    a. Create `/Users/cmdb/qbb2020-answers/day3-hw`.

    b. Make a working copy of the following files.  Check that the size of each file matches the original.

    ```
    /Users/cmdb/qbb2020/data/K27me3.bed
    /Users/cmdb/qbb2020/data/K4me3.bed
    /Users/cmdb/qbb2020/data/K9me3.bed
    /Users/cmdb/data/genomes/BDGP6.Ensembl.81.gtf
    ```

    c. Download a copy of the 588 MB file `SRR072893.bam` using the following command.

    ```
    wget https://bx.bio.jhu.edu/track-hubs/cmdb/SRR072893.bam
    ```

    d. Create an index file for `SRR072893.bam` that IGV and other programs will require for fast access.

    ```
    samtools index /Users/cmdb/qbb2020-answers/day3-hw/SRR072893.bam
    ```

    e. Record your file sizes by saving the output of `ls` into a file named `directory.txt`.

  - **Note for Exercise 1, only git add, commit, and push `directory.txt`**

2. Visualize the region surrounding Sxl using IGV:

    a. Install igv using conda and start by running `igv`.

    b. Switch the active genome in the upper left from `Human hg19` to `D. melanogaster (dm6)`.

    c. Load using `File > Load from File ...` the histone modifications (`K4me3.bed`, `K9me3.bed`, and `K27me3.bed`) and RNA abundance in stage 10 male embryo (`SRR072893.bam`).

    d. Visualize the region surrounding Sxl by entering `chrX:7,040,000-7,141,000` into the top search box.

    e. Adjust visibility by changing `View > Preferences > Alignments > Visibility range` to 100.

    f. Create an image using `File > Save Image`.

  - **Note for Exercise 2 only git add, commit, and push your saved image**

3. Report the number times each feature appears in column 3 of `BDGP.Ensembl.81.gtf` using `cut`, `sort`, `uniq`, and any other commands you'd like to include. The file you direct stdout to should be named `features.txt`

    - You should have exactly 8 lines in a file named `features.txt`.

  - **Note for Exercise 3 only git add, commit, and push `features.txt`**

4. You have 3 bed files (`K4me3.bed`, `K9me3.bed`, and `K27me3.bed`). **For each of these `.bed` files,** create a single file (`k4.info`, `k9.info`, and `k27.info`) with the total number of intervals on each chromosome.

  - **Note for Exercise 4 only git add, commit, and push `k4.info`, `k9.info`, and `k27.info`**

5. Report the first 10 intervals on 2L for `K4me3.bed`.

    - Note that the first interval is at `5082` not `10003708`.

  - **Note for Exercise 5 only git add, commit, and push the output file with the first 10 interval on 2L**

## Advanced Exercise

Use BEDTools to solve these exercises.  See below for more information about BEDTools.

0. Install bedtools using conda

1. Sort each `.bed` file (e.g. `K4me3.sorted.bed`)

    - You do not have to `git commit` these

2. Calculate Jaccard statistics to understand similarity between each histone modification

    - Create a single file `jaccard.txt`, prefixing each `bedtools` output with the output of `echo "*** mark1 vs mark2"` e.g.

        ```
        *** K4 vs K9
        intersection	union-intersection	jaccard	n_intersections
        342795	26879767	0.0127529	189
        *** K4 vs K27
        ```
  - **Note for AE2 only git add, commit, and push `jaccard.txt`**

3. Annotate each interval in `K4me3.bed` by finding the closest gene in `/Users/cmdb/qbb2020/data/genes.bed`

    - Ensure that you have the same number lines as the original `K4me3.bed` file (hint: how would you handle ties?)

    - `git commit` the last 10 lines, keeping your results in the [.bed format](https://genome.ucsc.edu/FAQ/FAQformat.html#format1) with gene in column 4 and distance in column 5 e.g. (This line is your note for AE3!)

        ```
        2L	5082	6616	CG11023	913
        2L	17024	18025	l(2)gl	0
        2L	18319	18506	l(2)gl	0
        ```

4. Using the annotated file you just made (e.g. `K4me3.annot.bed`), find the 10 intervals with the most RNA-seq reads in `SRR072893.bam`

    - Visually confirm using IGV

## References

#### Unix

- [Shorter](http://bxlab.github.io/cmdb-bootcamp/cheatsheet/unix.html) and [longer](https://github.com/0nn0/terminal-mac-cheatsheet) Unix cheat sheet
- Wikipedia list of [Unix commands](https://en.wikipedia.org/wiki/List_of_Unix_commands)
- Software Carpentry "[The Unix Shell](http://swcarpentry.github.io/shell-novice/)"

#### BEDTools

- Full list of *bedtools* [subcommands](https://bedtools.readthedocs.io/en/latest/content/bedtools-suite.html)
- bedtools [Tutorial](http://quinlanlab.org/tutorials/bedtools/bedtools.html)

#### Git

- [Short](http://bxlab.github.io/cmdb-bootcamp/cheatsheet/git.html) Git cheat sheet
- Software Carpentry "[Version Control with Git](http://swcarpentry.github.io/git-novice/)"
- Example
    ```
    $ cd ~/qbb2019-answers/day1-lunch
    $ find /Users/cmdb/data > data_contents
    $ git status
    $ git add data_contents
    $ git status
    $ git commit
    $ git push
    ```
