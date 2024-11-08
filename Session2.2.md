# Hands-on Manual Genome Curation Physalia course - Day 1

**Session 2.2: Decontaminating your assembly**

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
https://drive.google.com/drive/folders/1vyRID2npv7Q6FTpKHLxXkle_fXS7jowJ?usp=share_link

You are going to use in the command-line only the region between the last slash and the question mark, like this: 1vyRID2npv7Q6FTpKHLxXkle_fXS7jowJ

So, the command-line will be like this:

```
gdown --folder 1vyRID2npv7Q6FTpKHLxXkle_fXS7jowJ

```

B. If you are running it locally, you should download data from Google Drive using the link above or use gdown in your laptop terminal.


## Visualize the following datasets in Sanger BTK viewer (https://grit-btk.tol.sanger.ac.uk) 

- Easy: daNymPelt1.20241015.hap2.fa (dicot)
- Medium: icMagCera1.20240711.hap1.fa (coleoptera)
- Hard: wsRidPisc1.20240921.haplotigs.fa (annelid)

 1. Which steps would you follow to remove prokaryote contamination?
 2. And eukaryotic one?
 3. Have you found remaining organelle scaffolds?

Now have a look at the decontaminated fasta files you just downloaded in Gitpod. Check if the number of scaffolds changed and if some of the scaffolds you detected as potential contamination were removed from the decontaminated fasta files.

> [!TIP]
> You can use 

```

grep -c <decont_fasta>

```

> for counting how many scaffolds you have in your assembly.