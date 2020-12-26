# Test BWA

what happens when a read maps to more than one location?

## create test genome

    echo ">chr1" > genome.fa
    head -n 10000 ~/Sequences/ref_genomes/A_thaliana/TAIR10_chr1.fas | tail -n 200 >> genome.fa
    echo ">chr1dup" >> genome.fa
    head -n 10000 ~/Sequences/ref_genomes/A_thaliana/TAIR10_chr1.fas | tail -n 100 >> genome.fa

## create some reads

    git clone https://github.com/lh3/wgsim.git
    cd wgsim
    gcc -g -O2 -Wall -o wgsim wgsim.c -lz -lm
    
    cd ../
    