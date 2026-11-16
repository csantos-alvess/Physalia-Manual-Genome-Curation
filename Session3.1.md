# Hands-on Manual Genome Curation Physalia course - Day 2

**Session 3: Beginning manual curation (Single haplotype curation)**

Please find today's slides at [Session_3_Beginning Manual Curation.pdf](https://github.com/epaule/Physalia-Manual-Genome-Curation/blob/main/docs/Session_3_Beginning%20Manual%20Curation.pdf).

Now you need to download the data we are going to use in this session. You can download it from [here](https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_2.tar.xz) locally to your laptop and unzip it. As example:
```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_2.tar.xz
tar xvfJ Day_2.tar.xz
```

**Start practicing manual curation on 3 insect genomes. These will be all single haplotype maps.**

Choose one of the following to start:

- icSchPect1 (coleoptera)
- icPolPter2 (coleoptera)
- icSchGiga1 (lepidoptera)
  
1) Are these genomes are from homogametic or heterogametic samples?
2) Could you identify and assign the sex chromosomes?

> [!TIP]
> For sex chromosomes identification you can use, whichever is available:
  > - Nucmer output files - use https://dot.sandbox.bio to visualize the results.
  > - PacBio reads coverage (for heterogametic ones, if this is the case).
  > - BUSCO synteny plot

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Assigned the sex chromosome 
> 3. Added metadata
> 4. Painted chromosomes
> 5. Generated AGP file
