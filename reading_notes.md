# Reading Notes: Attention Is All You Need (arXiv 1706.03762)

**Paper:** "Attention Is All You Need" — Vaswani et al., arXiv 1706.03762

## Summary

At the time this paper was written, the dominant sequence transduction models were built from complex recurrent or convolutional networks, and the best-performing ones additionally connected their encoder and decoder through an attention mechanism. This paper takes that idea to its logical extreme: the authors propose the Transformer, an encoder-decoder architecture built **entirely out of attention**, dispensing with recurrence and convolutions altogether. Because nothing in the model depends on processing tokens one-by-one in sequence, it is far more parallelizable than recurrent alternatives and needs significantly less time to train — while still achieving higher translation quality. The authors also show the architecture generalizes beyond translation by applying it to English constituency parsing, both with large and with limited training data.

## Headline translation results

| Task | Result |
| --- | --- |
| WMT 2014 English-to-German | **28.4 BLEU**, improving over the existing best results (including ensembles) by over 2 BLEU |
| WMT 2014 English-to-French | **41.8 BLEU**, a new single-model state of the art, trained for 3.5 days on eight GPUs — a small fraction of the training cost of the best models in the literature |

## Paper outline

1. **Introduction** — motivation and the paper's contributions
2. **Background** — prior sequence transduction models and related work
3. **Model Architecture** — the Transformer encoder-decoder design and its components
4. **Why Self-Attention** — why self-attention is preferred over recurrent and convolutional layers
5. **Training** — training data, hardware, schedule, and optimization
6. **Results** — machine translation results plus generalization to constituency parsing
7. **Conclusion** — summary and future directions
8. **Attention Visualizations** — appendix showing example attention patterns
