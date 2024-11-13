# Hands-on Manual Genome Curation Physalia course - Day 4

**Session 4: Challenging genomes to curate and strategies to deal with them**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [slides_bga_2024.pdf](slides_bga_2024.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 

```
export PATH=/workspace/mambaforge/bin/:$PATH

```


Now you need to download the data we are going to use in this session. You can download it to GitPod or locally to your laptop, as follows:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_4.tar.xz
```

Then:

```
tar xvfJ Day_4.tar.xz
```

If you are locally, you also need to download ```rapid_curation ``` scripts from here: https://github.com/sanger-tol/rapid-curation/blob/main/

## For this session, we will focus on microchromosomes.

Today, we are going to start with single haplotype maps and tomorrow we will move to dual curation ones.

Choose one of the bird assemblies to work on. These maps already have MicroFinder results on them, look at the top of the maps:

- bBucCla1 ``` (merged_first_pass_max_20Mb_hr.pretext) ```
- bAnsBra1 ``` (bAnsBra1_1_micros_hr.pretext) ```
- sHetFra1 (shark): find the nucmer files at https://drive.google.com/drive/folders/16KKCKawhKe_Fa3HwSNIsWZQ5jKjgbdcW?usp=share_link


Both species have a karyotype of n = 40.

**The goal here is you to work on the micro and sex chromosomes as much as you can, saving time at the end to generate the curated fasta file.**

> [!IMPORTANT]
> 1. If you are using Gitpod, choose the high resolution map to curate. As microchromosomes are small, you can have a greater magnification on them when you use highres maps.
> 2. If you are running locally, highres maps usually require much more RAM memory to load than normal resolution ones. In case your laptop cannot open a high res map, choose the normal res one or move to Gitpod.


> [!TIP]
> 1. Use the nucmer alignments to assemble the micros (identify the order the scaffolds go to make a full micro)
> 2. Go to tolqc (https://tolqc.cog.sanger.ac.uk) and check the data available for your assembly.


Question 1. How many chromosomes can you see assembled when you open the map? Is it close to the karyotype number? Try to identify and assemble the microchomosomes.

Question 2. Are you curating a homogametic or heterogametic sex individual? Try to identify and assign sex chromosomes. Can you see something unexpected about the sex chromosomes?

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

## Generating the curated fasta file


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

**A. Single hap curation:**

```
python /workspace/rapid-curation/multi_join.py \
-t curated_HAP1.tpf \
-f original.fa \
-c chrs.csv \
-o <output_name>

```
If you have detected haplotigs during the curation process, you can provide the ```-d``` option to the script, followed by the ```curated_Haplotigs.tpf``` file generated from ptt.


**Output files from single hap curation:**

```
<tolid>.1.additional_haplotigs.curated.fa
<tolid>.1.inter.csv
<tolid>.1.primary.chromosome.list.csv
<tolid>.1.primary.curated.fa
```
