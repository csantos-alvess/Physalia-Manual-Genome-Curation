# Hands-on Manual Genome Curation Physalia course - Day 2

**Session 3: Beginning manual curation (Single haplotype curation)**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [slides_bga_2024.pdf](slides_bga_2024.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 

```
export PATH=/workspace/mambaforge/bin/:$PATH

```

Now you need to download the data we are going to use in this session:

A. From gitpod:

```
gdown --folder <link_to_folder_in_google_drive>

```

For example, for the following link:
https://drive.google.com/drive/folders/1LzfDf1dW6OCSfvUp4SkYpgRl24G8fSEE?usp=share_link

You are going to use in the command-line only the region between the last slash and the question mark, like this: 1LzfDf1dW6OCSfvUp4SkYpgRl24G8fSEE

So, the command-line will be like this:

```
gdown --folder 1LzfDf1dW6OCSfvUp4SkYpgRl24G8fSEE

```

B. If you are running it locally, you should download data from Google Drive using the link above or use gdown in your laptop terminal.


**Start practicing manual curation on 3 insect genomes. These will be all single haplotype maps.**

Choose one of the following to start:

- ilCalCecr1 (lepdopitera)
- icPolPter2 (coleoptera)
- ilCycPunc2 (lepdopitera)

Check if these genomes belong to homogametic or heterogametic samples and try to identify and assign sex chromosomes. You may use Nucmer output files or PacBio reads coverage.

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file
