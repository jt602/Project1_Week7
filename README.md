# Project1_Week7_SequenceAnalysis
## Purpose
The aim of this project is to identify, analyse and summarise DNA mutations present in input data, allowing comparisons to be drawn between the control and treatment group's various samples. The biological query it aims to answer is to process the first 200 nucleotides in NGS (Next Generation Sequencing) reads, which by hand would take a long time to do. 

## How To Run
To run this program open the colab commit <i><b>"c7147_project_1_assessment.ipynb"</b></i>. Then either <i><b>"run all"</b></i> or run the code cells individually. The last coding cell is where all the previously separately established functions can be called in one go (after they are run separately, otherwise the functions are not defined.

## Inputs & Outputs
Input data (read) should include a readID, sample name, experiment group (e.g. treated, control), DNA sequence and be submitted in this format: (csv)

<pre>_read_0001,sample1,treatment,ATGGCTAAAGACAATTACATAACATACACGTCAGCACGAAACTTGTTGGCCCAGTGTGAATCGCTTAAGGGTGTAAGTGTGATGCATACGCCTTTACACGCTGTGTCCACCCCATCGGACTGGCATTTTTATTACACTCAGAAACAGAACTCGGGTAATTTTGACAGGTCACGCAGAGGCGCGCCCTCCAGTGCGTAGGG_</pre>

And the corresponding reference data: (txt)

<pre>_>reference
ATGGCTAAAGACAATTACATAACATACACGTCAGCACGAAACTTGTTGGCCCAGTGTGAATCGCTTAAGGGTGTAAGTGTGATGCATACGCCTTTAACGGCTGTGTCCACCCCATCGGACTGGCATTTTTATTACACTCAGAAACAGAACTCGGGTAATTTTGACAGGTCACGCAGAGGCGCGCCCTCCAGTGCGTAGGG_</pre>

The output of this program and its subsequent functions includes valid/invalid read counts, mismatch percentages, substitutions, mutated base positions and the top 3 mutated positions. The program also compares treated vs control groups using the provided statistical test setup code as well as derived subfunctions, outputting mean difference and p-values.

## Code Design

According to the provided assignment brief, the program was divided into five functions: validate_read(), find_mutations(), analyse_reads(), summarise_samples & compare_positions(). This makes it easier to catch errors as its not one large chunk of code. Dictionaries were also used in place of lists as it made count and len functions reliable and allowed easy comparison. 

A list was used however, to record any Errors the code came across, e.g. wrong_length, and invalid sequences. This allows the user to see if any errors occur, and at what position, instead of the code breaking or ignoring the errors, it calls them to attention.

## Testing
_Input Test Example:_
<pre>assert sample_summary["sampleA"]["valid_reads"] == 3 
assert sample_summary["sampleB"]["valid_reads"] == 1
assert sample_summary["sampleA"]["invalid_reads"] == 0
assert sample_summary["sampleB"]["invalid_reads"] == 2
print("1. Valid and Invalid Test Passed (counts are correct)")</pre>
**Checks that the code recorded the correct number of valid and invalid reads**

_Edge Case Test Example:_
<pre>assert sample_summary["sampleA"]["position_counts"] == {1: 1, 4: 1}
assert sample_summary["sampleA"]["top_positions"] == [1, 4]
assert sample_summary["sampleB"]["top_positions"] == []
print("4. mutation positions test passed")</pre>
**Checks that there are a correct number of top_positions and that sample B doesn't have any top positions as it is the control and therefore has very low mismatch percentages**

_Invalid Input Test Example:_
<pre>try:
  find_mutations(42069, "ATGC")
  assert False, "TypeError Expected"
except TypeError:
  print("Invalid Input TypeError Identified")</pre>

**Checks that if the input is not in the correct format, an error is raised**
