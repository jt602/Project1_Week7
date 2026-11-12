# Project1_Week7_SequenceAnalysis
## Purpose
The aim of this project is to identify, analyse and summarise DNA mutations present in input data, allowing comparisons to be drawn between the control and treatment group's various samples. The biological query it aims to answer is to process the first 200 nucleotides in NGS (Next Generation Sequencing) reads, which by hand would take a long time to do. 

## How To Run
To run this program open the colab commit <i><b>"c7147_project_1_assessment.ipynb"</b></i>. Then either <i><b>"run all"</b></i> or run the code cells individually. The last coding cell is where all the previously separately established functions can be called in one go (after they are run separately, otherwise the functions are not defined.

## Inputs & Outputs
Input data (read) should include a readID, sample name, experiment group (e.g. treated, control), DNA sequence and be submitted in this format:

_read_0001,sample1,treatment,ATGGCTAAAGACAATTACATAACATACACGTCAGCACGAAACTTGTTGGCCCAGTGTGAATCGCTTAAGGGTGTAAGTGTGATGCATACGCCTTTACACGCTGTGTCCACCCCATCGGACTGGCATTTTTATTACACTCAGAAACAGAACTCGGGTAATTTTGACAGGTCACGCAGAGGCGCGCCCTCCAGTGCGTAGGG_

The output of this program and its subsequent functions includes valid/invalid read counts, mismatch percentages, substitutions, mutated base positions and the top 3 mutated positions. The program also compares treated vs control groups using the provided statistical test setup code as well as derived subfunctions, outputting mean difference and p-values.

## Code Design


## Testing
