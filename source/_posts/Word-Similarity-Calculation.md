---
title: Word Similarity Calculation
date: 2019-04-09 00:16:20
tags: [ Word Distance, NLP]
---

## Word Similarity

### Introduction

Word similarity calculation on the dataset [Mturk-771](http://www2.mta.ac.il/~gideon/mturk771.html), [MEN](https://www.jair.org/index.php/jair/article/view/10857), [RW-STANFORD](https://nlp.stanford.edu/~lmthang/morphoNLM/), [SimLex-999](https://arxiv.org/pdf/1408.3456), [SimVerb-3500](https://arxiv.org/abs/1608.00869).

1. path_similarity, wup_similarity, lch_similarity, res_similarity, jcn_similarity, lin_similarity (WordNet-based)
2. WebJaccard, WebOverlap, WebDice, WebPMI, NGD (Google Search Based)
3. LSA-Wikipedia, LDA-Wikipedia (Wikipedia-based)
4. Word2Vec, Fasttext, GloVe, ELMo, BERT (Representation Learning)

Github Repo Link: [https://github.com/leelaylay/Word_Similarity](https://github.com/leelaylay/Word_Similarity)

## Results

All results are calculated in Spearman's rank correlation coefficient.

| Method          | MTurk-771  | MEN        | RW-STANFORD | SimLex-999 | SimVerb-3500 |
| --------------- | ---------- | ---------- | ----------- | ---------- | ------------ |
| Path            | 0.4985     | 0.3342     | -0.0003     | 0.4370     | 0.4538       |
| Wup             | 0.4550     | 0.3589     | 0.0252      | 0.4137     | 0.4080       |
| Lch             | 0.4960     | 0.3544     | 0.0086      | 0.4097     | 0.4493       |
| Resnik          | 0.4168     | 0.3610     | 0.0539      | 0.3595     | 0.4471       |
| Jcn             | 0.4823     | 0.3343     | 0.0019      | 0.4574     | 0.4629       |
| Lin             | 0.4931     | 0.3338     | 0.0147      | 0.4047     | **0.4712**   |
| WebJaccard      | 0.3272     | 0.4516     | 0.1503      | 0.0871     | 0.0021       |
| WebOverlap      | 0.2346     | 0.3953     | 0.0416      | 0.0778     | 0.0235       |
| WebDice         | 0.3351     | 0.4365     | 0.1610      | 0.0871     | 0.0010       |
| WebPMI          | 0.3272     | 0.4316     | 0.1503      | 0.0871     | 0.0021       |
| NGD             | 0.3282     | 0.4671     | -0.2297     | 0.1592     | -0.0446      |
| LSA-Wikipedia   | 0.5851     | 0.4663     | 0.1838      | 0.2094     | 0.1038       |
| LDA-Wikipedia   | 0.1936     | 0.2815     | 0.0265      | 0.0164     | 0.0165       |
| Word2Vec        | 0.6713     | 0.7321     | 0.4527      | 0.4420     | 0.3635       |
| FastText        | **0.7529** | **0.8362** | **0.5713**  | **0.4644** | 0.3649       |
| GloVe           | 0.7152     | 0.8016     | 0.4512      | 0.4083     | 0.2832       |
| ELMo            | 0.6938     | 0.4698     | 0.2570      | 0.3151     | 0.2407       |
| BERT(Embedding) | 0.0019     | 0.0668     | 0.2021      | 0.0801     | 0.0487       |
