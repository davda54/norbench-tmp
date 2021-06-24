# NorBench
This repository contains a preliminary attempt at compiling a comprehensive set 
natural language understanding (NLU) benchmarks for Norwegian.

We list the existing test sets, their recommended evaluation metrics 
and provide links to the evaluation code (where available). 
Currently we only link to the original datasets, 
but in the future we plan to provide their standardized versions for easier benchmarking.   

## Mainstream NLP tasks

| Task                        | Test Set               | Metrics| Evaluation code |
|-----------------------------|------------------------|--------|-----------------|
|PoS tagging                  |[Bokmaal](https://github.com/UniversalDependencies/UD_Norwegian-Bokmaal) / [Nynorsk](https://github.com/UniversalDependencies/UD_Norwegian-Nynorsk) / [Dialects](https://github.com/UniversalDependencies/UD_Norwegian-NynorskLIA)|        |                 |
|Dependency parsing           |[Bokmaal](https://github.com/UniversalDependencies/UD_Norwegian-Bokmaal) / [Nynorsk](https://github.com/UniversalDependencies/UD_Norwegian-Nynorsk) / [Dialects](https://github.com/UniversalDependencies/UD_Norwegian-NynorskLIA)                        |        |                 |
|Named entity recognition     |[NorNE Bokmaal](https://github.com/ltgoslo/norne/tree/master/ud/nob) / [NorNE Nynorsk](https://github.com/ltgoslo/norne/tree/master/ud/nno)                        |        |                 |
|Sentence-level polarity      |[NoReC Sentences](https://github.com/ltgoslo/norec_sentence/)|        |                 |
|Structured sentiment analysis|[NoReC_fine](https://github.com/ltgoslo/norec_fine)                        |        |                 |
|Negation cues and scopes     |[NoReC_neg](https://github.com/ltgoslo/norec_neg/)                        |        |                 |
|Co-reference resolution      |annotation ongoing                        |        |                 |


## Lexical tasks

| Task                        | Test Set               | Metrics| Evaluation code |
|-----------------------------|------------------------|--------|-----------------|
|Synonym detection            |[Norwegian Synonymy](https://github.com/ltgoslo/norwegian-synonyms)                        |        |                 |
|Analogical reasoning         |[Norwegian Analogy](https://github.com/ltgoslo/norwegian-analogies)                        |        |                 |
|Word-level polarity          |[NorSentLex](https://github.com/ltgoslo/norsentlex)                        |        |                 | 
|Word sense disambiguation in context|[Norwegian WordNet](https://www.nb.no/sprakbanken/en/resource-catalogue/oai-nb-no-sbr-27/)                 |        |                 |

## Text classification tasks

| Task                        | Test Set               | Metrics| Evaluation code |
|-----------------------------|------------------------|--------|-----------------|
|Synonym detection            |                        |        |                 |
|Analogical reasoning         |                        |        |                 |
|Word-level polarity          |                        |        |                 | 
|Word sense disambiguation in context|                 |  