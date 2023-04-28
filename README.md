# NorBench
This repository contains an emerging attempt at compiling a comprehensive set 
of NLP benchmarks for Norwegian, together with evaluation of the respective performance of various Norwegian language models on these tasks. 

[See the leaderboard](leaderboard.md)

We list the existing test sets, their recommended evaluation metrics
and provide links to the original evaluation code (where available).
The `evaluation_scripts` directory contains the recommended ready-to-use evaluation scripts for the main tasks
(warning: work in progress!)

The tasks which are currently used in the NorBench leader-board are **emphasized in bold**.

Currently, we only link to the original datasets,
but in the future we plan to provide their standardized versions for easier benchmarking.

## Mainstream NLP tasks

| Task                                                           | Test Set                                                                                                                                                                                                                           | Metrics                                    | Evaluation code                                                                                                                                                                                                                    |
|----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **PoS tagging**                                                | [Bokmaal](https://github.com/UniversalDependencies/UD_Norwegian-Bokmaal) / [Nynorsk](https://github.com/UniversalDependencies/UD_Norwegian-Nynorsk) / [Dialects](https://github.com/UniversalDependencies/UD_Norwegian-NynorskLIA) | Macro F1 UPOS/XPOS                         | [CoNLL 2018 shared task evaluation script](https://universaldependencies.org/conll18/conll18_ud_eval.py)                                                                                                                           |
| **Dependency parsing**                                         | [Bokmaal](https://github.com/UniversalDependencies/UD_Norwegian-Bokmaal) / [Nynorsk](https://github.com/UniversalDependencies/UD_Norwegian-Nynorsk) / [Dialects](https://github.com/UniversalDependencies/UD_Norwegian-NynorskLIA) | Unlabeled/Labeled Accuracy Score (UAS/LAS) | [CoNLL 2018 shared task evaluation script](https://universaldependencies.org/conll18/conll18_ud_eval.py)                                                                                                                           |
| **Named entity recognition**                                   | [NorNE Bokmaal](https://github.com/ltgoslo/norne/tree/master/ud/nob) / [NorNE Nynorsk](https://github.com/ltgoslo/norne/tree/master/ud/nno)                                                                                        | Entity-level exact match F1 (strict)       | [Batista's re-implementation of the SemEval 2013 evaluation script](https://github.com/davidsbatista/NER-Evaluation)                                                                                                               |
| **Sentence-level polarity** (ternary sentiment classification) | [NoReC_sentence](https://github.com/ltgoslo/norec_sentence/)                                                                                                                                                                       | Macro averaged F1                          | [classifier](https://github.com/ltgoslo/norbench/blob/main/evaluation_scripts/sa_classification.py)                                                                                                                                |
| **Targeted sentiment analysis**                                | [NoReC_tsa](https://github.com/ltgoslo/norec_tsa)                                                                                                                                                                                  | Entity-level exact match F1 (strict)       | [Batista's re-implementation of the SemEval 2013 evaluation script](https://github.com/davidsbatista/NER-Evaluation)                                                                                                               |
| **Linguistic acceptance**                                      | [NoCoLa](https://github.com/ltgoslo/nocola/tree/main/datasets)                                                                                                                                                                     | MCC                                        | [repo](https://github.com/ltgoslo/nocola/tree/main/evaluation)                                                                                                                                                                     |
| **Question answering**                                         | [NorQuaD](https://github.com/ltgoslo/NorQuAD)                                                                                                                                                                                      | token-level F1                             | [repo](https://github.com/ltgoslo/NorQuAD/tree/main/evaluation)                                                                                                                                                                    |
| **Machine translation from Bokmål to Nynorsk**                 | [Omsetjingsminne frå Nynorsk pressekontor](https://www.nb.no/sprakbanken/ressurskatalog/oai-nb-no-sbr-47/), [Omsetjingsminne frå Målfrid](https://www.nb.no/sprakbanken/ressurskatalog/oai-nb-no-sbr-78/)                          | SacreBLEU                                  | [TorchMetrics](https://torchmetrics.readthedocs.io/en/stable/text/sacre_bleu_score)                                                                                                                                                |
| Structured sentiment analysis                                  | [NoReC_fine](https://github.com/ltgoslo/norec_fine)                                                                                                                                                                                | Sentiment Graph F1                         | [Semeval 2022 evaluation script](https://github.com/jerbarnes/semeval22_structured_sentiment/blob/master/evaluation/evaluate_single_dataset.py)                                                                                    |
| Negation cues and scopes                                       | [NoReC_neg](https://github.com/ltgoslo/norec_neg/)                                                                                                                                                                                 | StarSem Full Negation F1                   | [StarSem Perl script](https://github.com/ltgoslo/norec_neg/blob/main/modeling/evaluation/eval.cd-sco.pl)                                                                                                                           |
| Co-reference resolution                                        | NARC (annotation ongoing)                                                                                                                                                                                                          | MUC, $B^3$, CEAFE, LEA                     | [evaluation notebook NARC](https://github.com/ltgoslo/Norwegian-Coreference-Corpus/blob/f077b9de830d753b04688558c6f46157ab8fefd0/code/notebooks/evaluation.ipynb) (using [corefeval](https://github.com/tollefj/coreference-eval)) |


## Text classification tasks

| Task                                                           | Test Set                                                    | Metrics           | Evaluation code                                                                                     |
|----------------------------------------------------------------|-------------------------------------------------------------|-------------------|-----------------------------------------------------------------------------------------------------|
| **Document-level polarity** (ternary sentiment classification) | [Norwegian Review Corpus](https://github.com/ltgoslo/norec) | Macro averaged F1 | [classifier](https://github.com/ltgoslo/norbench/blob/main/evaluation_scripts/sa_classification.py) |
| Political affiliation detection                                | [Talk of Norway](https://github.com/ltgoslo/talk-of-norway) |                   |                                                                                                     |
| Dialect classification in tweets                               | [NorDial](https://github.com/jerbarnes/norwegian_dialect)   | Macro averaged F1 | [sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html)          |


## Lexical tasks

| Task                                         | Test Set                                                                                   | Metrics                        | Evaluation code                                                                                            |
|----------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------|
| Synonym detection                            | [Norwegian Synonymy](https://github.com/ltgoslo/norwegian-synonyms)                        |                                | Can be used for contextualized models with lexical substitution                                            |
| Analogical reasoning*                        | [Norwegian Analogy](https://github.com/ltgoslo/norwegian-analogies)                        |                                |                                                                                                            |
| Word-level polarity*                         | [NorSentLex](https://github.com/ltgoslo/norsentlex)                                        | Accuracy                       | [sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html)           |
| Word sense disambiguation in context (WSDiC) | [Norwegian WordNet](https://www.nb.no/sprakbanken/en/resource-catalogue/oai-nb-no-sbr-27/) | Averaged macro F1              | [Preliminary example](https://github.com/ltgoslo/simple_elmo/blob/master/simple_elmo/examples/wsd_eval.py) |
| Lexical semantic change detection (LSCD)     | [NorDiaChange](https://github.com/ltgoslo/nor_dia_change)                                  | Spearman correlation, Accuracy | [SemEval'2020](https://github.com/akutuzov/semeval2020/blob/master/code/eval.py)                           |


_* Type-based (static) models only_
