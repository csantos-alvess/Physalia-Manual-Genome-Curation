# Hands-on Manual Genome Curation Physalia course - Day 3

**Session 3.2: Dual Curation and curated fasta file generation**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [slides_bga_2024.pdf](slides_bga_2024.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 

```
export PATH=/workspace/mambaforge/bin/:$PATH

```

Now you need to download the data we are going to use in this session. You can download it to GitPod or locally to your laptop, as follows:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_3.tar.xz
```

Then:

```
tar xvfJ Day_3.tar.xz
```

## Now we have 3 dual curation maps for curation:

Choose one of the following to work on:

- drRubCaes1 (dicot)
- idPolLara1 (diptera)
- ilEupHawo1 (lepidoptera)


Check if the insect genomes belong to homogametic or heterogametic samples and try to identify and assign sex chromosomes using Nucmer output files.

> [!IMPORTANT]
> We don't assign sex chromosomes to female diptera due to the high turnover rate.

> [!TIP]
> Go to tolqc (https://tolqc.cog.sanger.ac.uk) and check data available for your assembly. 
> 1. How much curation effort you expect to be necessary based on heretozygozity? 
> 2. Does the sex identified by tolqc matches the one you are seeing in the HiC map?
> 3. Are PacBio and HiC data from the same sample?


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

**B. Dual curation:**

```
curated_Haplotigs.tpf
curated_HAP1.tpf
curated_HAP2.tpf
chrs_HAP1.csv
chrs_HAP2.csv
curated.log

```

**Step 3. Run multi_join. This is what generates a new fasta file from the curation manipulations**

**A. Single hap curation:**

```
python /workspace/rapid-curation/multi_join.py \
-t curated_HAP1.tpf \
-f original.fa \
-c chrs.csv \
-o <output_name>

```
If you have detected haplotigs during the curation process, you can provide the ```-d``` option to the script, followed by the ```curated_Haplotigs.tpf``` file generated from ptt.

**B. Dual hap curation:**

```
python /workspace/rapid-curation/multi_join.py \
-t curated_HAP1.tpf \
-t2 curated_HAP2.tpf \
-f original.fa \
-c chrs_HAP1.csv \
-c2 chrs_HAP2.csv \
-o <output_name>

```

**Output files from single hap curation:**

```
<tolid>.1.additional_haplotigs.curated.fa
<tolid>.1.inter.csv
<tolid>.1.primary.chromosome.list.csv
<tolid>.1.primary.curated.fa
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





