# Hands-on Manual Genome Curation Physalia course - Day 1

**Session 2.2: Decontaminating your assembly**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [slides_bga_2024.pdf](slides_bga_2024.pdf).

Gitpod: https://gitpod.io/new/#https://github.com/sanger-tol/rapid-curation

If you are using GitPod, before clicking in 'Continue' choose 'Large' for the third option (class). Then click 'Continue'.

It will take around 2-3 minutes for Gitpod to load. After that, type in the terminal: 
export PATH=/workspace/mambaforge/bin/:$PATH

Now you need to download the data we are going to use in this session:

A. From gitpod:
gdown --folder <link_to_folder_in_google_drive>

For example, for the following link:
https://drive.google.com/drive/folders/1bQlNd-2eiaze1JHTsCX0ff_uJ4GpG9rd?usp=share_link

You are goind to use in the command-line only the region between the last slash and the question mark, like this: 1bQlNd-2eiaze1JHTsCX0ff_uJ4GpG9rd


## Visualize the following datasets in BTK Sanger BTK viewer (https://grit-btk.tol.sanger.ac.uk) 

Easy: daNymPelt1.20241015.hap2.fa (dicot)
Medium: icMagCera1.20240711.hap1.fa (coleoptera)
Hard: wsRidPisc1.20240921.haplotigs.fa (annelid)

Which steps would you follow to remove prokaryote contamination?
And eukaryotic one?
Have you found remaining organelle scaffolds?

Now have a look at the decontaminated fasta files you just downloaded in Gitpod. Check if the number of scaffolds changed and it scaffolds you detected as contamination were removed from the decontaminated fasta files.
