## windowHaplotyper

windowHaplotyper runs a sliding window through multiple aligned genes and counts the different haplotypes present.  The windows size must be set by the user.


Download and Usage
----------------------
windowHaplotyper is [perl](https://www.perl.org/) based and has no dependencies. You can directly download the repository and run it as follow:

```
$ perl /path/to/windowHaplotyper <gene.aln> <window Size> 
```

The input file needs to be in aligned fasta format, the default output of the common [MUSCLE](https://drive5.com/muscle/) aligner. The fasta header can contain any type of sign. The windows size need to be given as an integer.

The output is a table containing start of the window, end of window and the count of unique haplotypes inside each specific window.To detect regions of maximum diversity, the output can easily be sorted as follow:

```
$ perl /path/to/windowHaplotyper gene.aln 200 | sort -k1,1n -k3,3n 
```
