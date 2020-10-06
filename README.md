# ﻿The Circa Dataset

This repository contains the dataset of polar questions and indirect answers introduced in 
our EMNLP 2020 paper:
"[I'd rather just go to bed": Understanding Indirect Answers]()"

Please cite our paper if you use this data.

```
@InProceedings{louis_emnlp2020,
  author =      "Annie Louis and Dan Roth and Filip Radlinski",
  title =       ""{I}'d rather just go to bed": {U}nderstanding {I}ndirect {A}nswers",
  booktitle =   "Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing",
  year =        "2020",
}
```

## Introduction

Circa (meaning ‘approximately’) dataset aims to help machine learning systems to solve the problem of interpreting indirect answers to polar questions. The dataset contains pairs of yes/no questions and indirect answers, together with annotations for the interpretation of the answer. The data is collected in 10 different social conversational situations (eg. food preferences of a friend). Examples:

```
Are you vegan?
I love burgers too much. [No]

Do you like spicy food?
I put hot sauce on everything. [Yes] 

Would you like to go see live music?
If it’s not too crowded. [Yes, upon a condition]
```

Currently, the Circa annotations focus on a few classes such as ‘yes’, ‘no’ and ‘yes, upon condition’. The data can be used to build machine learning models which can replicate these classes on new question-answer pairs, and allow evaluation of methods for doing so. 


## Copyright


This dataset is the work of Annie Louis, Dan Roth, and Filip Radlinski from Google LLC, made available under the Creative Commons Attribution 4.0 License. A full copy of the license can be found at https://creativecommons.org/licenses/by-sa/4.0/


## Data Collection Method


The QA pairs and judgements were collected using crowd annotations in three phrases. We recruited English native speakers. The detailed annotation instructions are present in our EMNLP 2020 paper. Below we provide a brief overview.


Phase 1: In the first phase, we collected questions only. We designed 10 imaginary social situations which give the annotator a context for the conversation. Examples are:
```
	‘asking a friend for food preferences’
	‘meeting your childhood neighbour’
	‘your friend wants to buy a flat in New York’
```
Annotators were asked to suggest questions which could be asked in each situation, such that each question only requires a ‘yes’ or ‘no’ answer. 100 annotators produced 5 questions each for the 10 situations, resulting in 5000 questions. We manually filtered noisy questions  and removed redundant ones. 


Phase 2: Here we focused on eliciting answers to the questions. We sampled 3500 questions from our previous set (350 per social situation). For each question, we collected possible answers from 10 different annotators. The annotators were instructed to provide a natural phrase or a sentence as the answer and to avoid the use of explicit ‘yes’ and ‘no’ words. 


Phase 3: Finally the QA pairs (34,268) were given to a third set of annotators who were asked how the question seeker would likely interpret a particular answer. These annotators had the following options to choose from:
```
	* 'yes'
	* 'probably yes' / 'sometimes yes'
	* 'yes, subject to some conditions'
	* 'No'
	* 'probably no'
	* 'in the middle, neither yes nor no'
	* I am not sure how X will interpret Y's answer
```

## Corpus format


The dialogue corpus is in .tsv format.

Each row has 8 columns. All columns contain ASCII strings. An example is given below (each column is on a new line for clarity and is prepended with the column header). 

```
ID		    :	1	
Context		    :	X wants to know about Y's food preferences.
Question-X	    :	Are you vegan?
Canquestion-X       :   I am vegan.
Answer-Y	    :	I love burgers too much. 
Judgements	    :	no#no#no#no#no	
Gold standard 1	    :	no
Gold standard 2	    :	no
```
	

The columns indicate:

```
1. ID             : unique id for the question-answer pair

2. Context        : the social situation for the dialogue. One of 10 situations (see next section). Each situation is a dialogue between a person who poses the question (X) and the person who answers (Y). 

3. Question-X     : the question posed by X 

4. Canquestion-X  : a (automatically) rewritten version of question into declarative form Eg. Do you like Italian? --> I like Italian. See the paper for details.

5. Answer-Y       : the answer given by Y to X

6. Judgements     : the interpretations for the QA pair from 5 annotators. The value is a list of 5 strings, separated by the token ‘#’

7. Gold standard 1: a gold standard majority judgement from the annotators. The value is the most common interpretation and picked by at least 3 (out of 5 annotators). When a majority judgement was not reached by the above criteria, the value is ‘NA’

8. Gold standard 2: Here the labels ‘probably yes / sometimes yes’ and ‘probably no’ are mapped respectively to ‘yes’ and ‘no’ before computing the majority. Still the label must be given at least 3 times to become the majority choice. This method represents a less strict way of analyzing the interpretations. 

```




## The 10 Social Situations

The following are the situational contexts for the dialogs in our data. 

```
1. X wants to know about Y’s food preferences
2. X wants to know what activities Y likes to do during weekends. 
3. X wants to know what sorts of books Y likes to read. 
4. Y has just moved into a neighbourhood and meets his/her new neighbour X.  
5. X and Y are colleagues who are leaving work on a Friday at the same time. 
6. X wants to know about Y's music preferences. 
7. Y has just travelled from a different city to meet X. 
8. X and Y are childhood neighbours who unexpectedly run into each other at a cafe. 
9. Y has just told X that he/she is thinking of buying a flat in New York. 
10. Y has just told X that he/she is considering switching his/her job.
```


*Note:* These 10 social situations remain the same throughout our data collection. However they are phrased differently while eliciting questions, answers or when gathering the interpretation. Please see the exact prompts in the appendix section of our EMNLP 2020 paper.




## Changes

2020-10-06: EMNLP 2020 release version



## Contact

If you have any technical questions about our dataset, please contact us at circa@google.com

