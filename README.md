# project1-dna-sequence-analysis

#***Analysing NGS data to identify nucleotide mismatches and potential mutations:***

##*Project purpose*:

Developing a Python analysis of NGS data, to identify nucleotide mismatches, relative to a reference DNA sequence. The purpose being to compare samples treated with a genotoxic agent and untreated samples to assess potential mutations.

##*How to run the program:*

The analysis can be carried out using Google Colab, where the Python notebook can be opened and the provided <ins>*reference.txt*</ins>  and <ins>*reads.csv*</ins>  files uploaded. Once the data has been loaded, the consecutive  code cells should be *run in order* to identify nucleotide mismatches and analyse the results.

##*Inputs and Outputs:*

For this NGS analysis project, there were two input files depicting two  DNA sequences: 
<ins>*reference.txt*</ins> , a reference sequence of 200 nucleotides  and  <ins>*reads.csv*</ins>, a sequence with 6000 reads. These totalted to 6 biological samples: split into treatment and control groups whereby, three samples were treated with a genotoxic agent as to promote DNA mutation, and the other three samples remained untreated.

The outputs for this project included various aspects:
Validated reads (in addition to labelled invalid reads), nucelotide mismatches (alongside the percentage of these), alongside frequency of base substituions and  dictionaries/ lists which stored sumamries for samples such as their group or sequence. Furthermore, the 3 positions with highest frequency of mismatches was analysed, and statistical testing for each of the three positions occured (including Welch's t-test and p-values). These were  presented in the final tables.

##*Code design*

In order for the code to be manageable and easily readable, the colab notebook, (and hence this project) divides into 5 steps, each referring to a relatively different functions. The steps increase in complexity subsequently, and functions from earlier steps were  used to shortern code in future, hence avoiding repetition. Similarly, various comments were used to separte and describe different code blocks.
Functions included: 'validate_read()' which returns validity status of a sequence, 'ranked_positions()', a helper function which sorted mismatch frequency at various postions of nucleotides.
Dictionaries (i.e sample_results[sample]) were chosen to store read information about the samples including  mismatch counts, these were chosen instead of lists as keys prove to be more informative and organised.
I ensured various error handling was incorporated,for example , invalid reads  were labelled, and excluded from certain calculations. Try/except Zero division erros was also used to prevent division by 0 when sample had no valid reads- as a result 'None; would be returned. Another important mode of handling errors was in step 5 where conditional stamements had to be used to handle statistical comparisons which could not be calculated- which otherwise would cause a crash.


##*Testing*
In general, for testing, *assert* statements were used, to ensure the correct result is produced from my code. For example in Step1, I checked "ATN" against "ATG" using assert to test if invalid nucleotides were detected- idenitfying invalid reads correctly being an important test throughout the project. Another mode of testing validity  used was creating a simulated dataset containing both valid and invalid samples, in both steps 4 and 5,  to test if the exclusion of the invalid sample occurred.The fake dataset ensured my code would work for various samples, excluding the input for this project- making the code reproducible. A more generalised test I used throughout the project was checking for empty strings  to test the robustness of my code. 

