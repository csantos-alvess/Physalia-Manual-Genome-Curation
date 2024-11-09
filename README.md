# Manual-Genome-Curation-Physalia

# COURSE OVERVIEW
Our course will introduce biologists and bioinformaticians to the concepts of manual genome curation using PretextView, through theoretical knowledge and practical examples. We will start introducing the concept of Hi-C sequencing and why this data is important to genome curation. Some steps prior to genome curation also will be addressed, such as the sort of information we can obtain from assembly quality metrics and the relevance of decontaminating your assembly before curation. Points such as how to generate a genome curated fasta file and strategies used to curate more challenging genomes will also be explored during the course. Finally, we will show how to identify sex chromosomes and some additional tools helpful for curation. By the end of the course, students will be familiar with manual genome curation, enabling them to interpret and work with Hi-C maps. In addition, they will understand everything that is needed to deliver high-quality chromosome assemblies.

# TARGETED AUDIENCE & ASSUMED BACKGROUND
The course is aimed at scientists with a biological background interested in learning about manual genome curation using PretextView. There will be a mix of lectures and hands-on practical exercises and basic command line. Prior experience with the Unix command-line is highly recommended (mandatory for running scripts) and genome assembly experience is welcome but not required. You will need a 3-button mouse for the course.

# LEARNING OUTCOMES
Understand how the assembly and Hi-C data quality are vital for efficient genome curation.
Be able to interpret Hi-C heatmaps in PretextView and identify the edits necessary to fix assembly errors.
Use PretextView  and its features for manual curation.
How to obtain a genome curated fasta file using the Rapid Curation pipeline.
Become familiar with additional tools used to curate more challenging genomes (microchromosomes, high heterozygosity) and how to identify sex chromosomes.
 
PROGRAM
Day1 - 2-6 pm Berlin time

Session 1: Manual curation overview

What is genome curation?
Why is it necessary to curate genome assemblies?
Overview of tools, data and course outcomes
 
Session 2.1: What to infer from assembly quality metrics?

It may be an effective sign of how much curation your genome will need.
Assembly metrics overview:
 - Kmer distribution, genome size, completeness
 - Raw data metrics
 - What to expect when purging doesn’t work
 - Real gene duplication or retained haplotig duplication?
 - Phased assemblies

Session 2.2: Decontaminate your assembly before curation -Hands-on

Contaminant screening,why this is important
How to do it and some databases to query
How to run
 - FCS
 - Tiara
 - BUSCO
 - BTK


Day2 - 2-6 pm Berlin time

Session 3.1: Beginning manual curation

Analysis pipelines
 - Treeval
 - Curation pretext pipeline
Curation tools
 - PretextView
 - Rapid curation workflow
 - (Jbrowse)
 
 
Day3 - 2-6 pm Berlin time

Session 3.2: How to generate your own PretextView Hi-C maps

 -Step-by-step generating Hi-C contact map
 -Step-by-step generating additional data tracks
 -Why they are useful and necessary for curation
 - Ingesting tracks to your map.
How to use PretextView
How to produce the curated fasta file


Day4 - 2-6 pm Berlin time

Session 4: Challenging genomes to curate and strategies to work with them High repeat and heterochromatin content
Identifying microchromosomes (birds, sharks etc.)
High chromosome number
Haplotype phasing
Polyploid genomes
All haplotypes assembly curation
Sex chromosome identification challenges
Alignment approaches
 - Sequence synteny
 - BUSCO synteny
 
Day5 - 2-6 pm Berlin time

Session 5: Working on more challenging genomes.
Analyse assembly metrics and plots, decontaminate your assembly, manually curate the genome.
At the end, each group will discuss the analysed data and raise the main difficulties found during curation.

Q&A session
