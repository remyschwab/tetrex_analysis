# Variable k Analysis: Shell Command List


### Create Indexes
```shell
##k=3
rschwab@loki build % ./bin/tetrex index -k 3 -m aa -i hibf -o sprot_k3 ~/Desktop/sprot_split/*.fasta>real_short_k3.fa
Indexed 572617 sequences across 1024 bins.
Writing to disk... DONE

##k=4
rschwab@loki build % ./bin/tetrex index -k 4 -m aa -i hibf -o sprot_k4 ~/Desktop/sprot_split/*.fasta>real_short_k4.fa
Indexed 572612 sequences across 1024 bins.
Writing to disk... DONE

##k=5
rschwab@loki build % ./bin/tetrex index -k 5 -m aa -i hibf -o sprot_k5 ~/Desktop/sprot_split/*.fasta>real_short_k5.fa
Indexed 572588 sequences across 1024 bins.
Writing to disk... DONE

##k=6
rschwab@loki build % ./bin/tetrex index -k 6 -m aa -i hibf -o sprot_k6 ~/Desktop/sprot_split/*.fasta>real_short_k6.fa
Indexed 572547 sequences across 1024 bins.
Writing to disk... DONE

##k=7
rschwab@loki build % ./bin/tetrex index -k 7 -m aa -i hibf -o sprot_k7 ~/Desktop/sprot_split/*.fasta>real_short_k7.fa
Indexed 572511 sequences across 1024 bins.
Writing to disk... DONE

## Single Bin
./build/bin/tetrex index -m aa -i hibf -o sprot_single_bin ~/Desktop/uniprot_sprot.fasta
```

### Generate Runtimes
```shell
## k=3
while read regex;do ./build/bin/tetrex query build/sprot_k3.ibf $regex;done<regexs.txt 2>runtimes_k3.tsv

## k=4
while read regex;do ./build/bin/tetrex query build/sprot_k4.ibf $regex;done<regexs.txt 2>runtimes_k4.tsv

## k=5
while read regex;do ./build/bin/tetrex query build/sprot_k5.ibf $regex;done<regexs.txt 2>runtimes_k5.tsv

## k=6
while read regex;do ./build/bin/tetrex query build/sprot_k6.ibf $regex;done<regexs.txt 2>runtimes_k6.tsv

## Single Bin
while read regex;do ./build/bin/tetrex query sprot_single_bin.ibf $regex;done<regexs.txt 2>runtimes_single_bin.tsv
```

### Measure Runtimes and Complexities
```shell
## k=3
while read regex;do ./build/bin/tetrex query ./variable_k_idx/sprot_k3.ibf $regex 2>>runtimes_and_complex/runtimes_and_complex_k3.txt;done<../tetrex_analysis/variable_k/regexs.txt

## k=4
while read regex;do ./build/bin/tetrex query ./variable_k_idx/sprot_k4.ibf $regex 2>>runtimes_and_complex/runtimes_and_complex_k4.txt;done<../tetrex_analysis/variable_k/regexs.txt

## k=5
while read regex;do ./build/bin/tetrex query ./variable_k_idx/sprot_k5.ibf $regex 2>>runtimes_and_complex/runtimes_and_complex_k5.txt;done<../tetrex_analysis/variable_k/regexs.txt

## k=6
while read regex;do ./build/bin/tetrex query ./variable_k_idx/sprot_k6.ibf $regex 2>>runtimes_and_complex/runtimes_and_complex_k6.txt;done<../tetrex_analysis/variable_k/regexs.txt
```

