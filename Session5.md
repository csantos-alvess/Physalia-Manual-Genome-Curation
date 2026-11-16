# Hands-on Manual Genome Curation Physalia course - Day 5

**Session 5: Challenging genomes to curate and strategies to deal with them - Part 2**


Now you need to download the [data](https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_5.tar.xz we are going to use in this session.

```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_5.tar.xz
tar xvfJ Day_5.tar.xz
```


## Today, we are working on HiC maps which require more curation effort:

- pySymPilo4: protist with poor HiC and high chromosome number. ``` pySymPilo4_2_normal.pretext ```. Give a try on this puzzle!
- xbMysUnda1: mollusc with very good HiC, but a not very pretty phasing. See if you can recognize and fix some of the wrong phasing regions.

The fasta files for pretext-to-asm can be found here: https://drive.google.com/drive/folders/1_5AcmOaxSGtj7iyEfcHDVAAZIj_tWUXp?usp=sharing

**Which were the main difficulties you found while working on these genomes?**

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

## Generating fasta files for single and dual curation maps

Go back to Session 3.2 to remind how to generate the curated fasta files.
