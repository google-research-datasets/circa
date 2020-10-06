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

