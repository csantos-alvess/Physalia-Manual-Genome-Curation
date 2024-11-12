# Hands-on Manual Genome Curation Physalia course - Day 2

**Session 3: Beginning manual curation (Single haplotype curation)**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [Session_3_Beginning Manual Curation.pdf](Session_3_Beginning Manual Curation.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 

```
export PATH=/workspace/mambaforge/bin/:$PATH

```

Now you need to download the data we are going to use in this session. You can download it to GitPod or locally to your laptop, as follows:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_2.tar.xz
```

Then:

```
tar xvfJ Day_2.tar.xz
```

If you are locally, you also need to download ```rapid_curation ``` scripts from here: https://github.com/sanger-tol/rapid-curation/blob/main


**Start practicing manual curation on 3 insect genomes. These will be all single haplotype maps.**

Choose one of the following to start:

- icSchPect1 (coleoptera)
- icPolPter2 (coleoptera)
- ilCycPunc2 (lepdopitera)

Check if these genomes belong to homogametic or heterogametic samples and try to identify and assign sex chromosomes. You may use Nucmer output files or PacBio reads coverage.

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

In case you have some remaining time, choose one of the following assemblies to give it a try:
- drPruBrig1 (dicot)
- gfRusFagi1 (fungi)
- odPhaVent3 (sponge). Did you find anything suspicious in your map, such as potential contamination? Have a BTK at BTK to check.
