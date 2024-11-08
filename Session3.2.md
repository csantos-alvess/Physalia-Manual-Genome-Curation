# Hands-on Manual Genome Curation Physalia course - Day 3

**Session 3.2: Dual Curation and curated fasta file generation**

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
https://drive.google.com/drive/folders/1Ft_F2-KsqsAL2wRsFaG5nLHqxVl8-8d1?usp=share_link

You are going to use in the command-line only the region between the last slash and the question mark, like this: 1Ft_F2-KsqsAL2wRsFaG5nLHqxVl8-8d1

So, the command-line will be like this:

```
gdown --folder 1Ft_F2-KsqsAL2wRsFaG5nLHqxVl8-8d1

```

B. If you are running it locally, you should download data from Google Drive using the link above or use gdown in your laptop terminal.


## Now we have 3 dual curation maps for curation:

Choose one of the following to start:

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




