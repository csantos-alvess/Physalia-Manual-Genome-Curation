# Hands-on Manual Genome Curation Physalia course - Day 5

**Session 5: Challenging genomes to curate and strategies to deal with them - Part 2**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [slides_bga_2024.pdf](slides_bga_2024.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 

```
export PATH=/workspace/mambaforge/bin/:$PATH

```


Now you need to download the data we are going to use in this session. You can download it to GitPod or locally to your laptop, as follows:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_5.tar.xz
```

Then:

```
tar xvfJ Day_5.tar.xz
```

If you are locally, you also need to download ```rapid_curation ``` scripts from here: https://github.com/sanger-tol/rapid-curation/blob/main/



## Today, we are working on dual haplotype maps.

Below we have 3 challenging genomes and you can choose any of them to work on today. All of them are dual haplotype curation maps:

- bCalBor7: bird asembly with MicroFinder results already on the top of the map ``` (bCalBor1_hap1_micros_hr.pretext) ``` and ``` (bCalBor1_hap2_micros_hr.pretext) ```

> [!IMPORTANT]
> 1. Karyotype n = 40. 
> 2. The hap1 and hap2 maps should be curated side-by-side. You will need to have two PretextView windows side-by-side.
> 3. Look carefully at the sex chroms, does anything catch you attention?

- drUrtDioi1: tetrapoid dicot plant genome ``` (out.pretext) ```. Try to solve this puzzle!
- laLemMinu1: monocot plant genome with phasing issues and misassemblies ``` (laLemMinu1_4_normal.pretext) ``` . Pacience leads to perfection!


**Try your best, saving time at the end to generate the curated fasta file.**


> [!TIP]
> 1. Use the nucmer alignments to assemble the micros (identify the order the scaffolds go to make a full micro)
> 2. Go to tolqc (https://tolqc.cog.sanger.ac.uk) and check the data available for your assembly.

**Which were the main difficulties you found while working on these genomes?**

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

## Generating fasta files for single and dual curation maps


Go to the assembly directory.

**Step 1. Run rapid_split on your decontaminated, pre-curation fasta file to create a tpf:**

```

perl /workspace/rapid-curation/rapid_split.pl -fa <your_fasta>.fa

```

Now you have a .tpf file from your original fasta, named original.fa.tpf.


**Step 2. Run pretext-to-tpf (alias ptt):**

To run pretext-to-tpf type the alias ‘ptt’ in the terminal, as the following:

```
ptt -a original.fa.tpf -p <your_species>.agp_1 -o <output_name>.tpf -w -f

```


```
-w: overwrite 
-f: force to run and overwrite
```

Let's assume you chose to name your output file as 'curated'. Then, the output files will be:

**A. Single haplotype:**

```
curated_Haplotigs.tpf
curated_curated.tpf
chrs.csv

```

**Step 3. Run multi_join. This is what generates a new fasta file from the curation manipulations**

**B. Dual curation:**

```
curated_Haplotigs.tpf
curated_HAP1.tpf
curated_HAP2.tpf
chrs_HAP1.csv
chrs_HAP2.csv
curated.log
```


**Output files from dual curation:**

```
<tolid>.hap1.1.all_haplotigs.curated.fa
<tolid>.hap1.1.inter.csv
<tolid>.hap1.1.primary.chromosome.list.csv
<tolid>.hap1.1.primary.curated.fa
<tolid>.hap2.1.all_haplotigs.curated.fa
<tolid>.hap2.1.inter.csv
<tolid>.hap2.1.primary.chromosome.list.csv
<tolid>.hap2.1.primary.curated.fa
```
