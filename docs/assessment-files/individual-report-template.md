# Individual Contribution Report — ISY503 Assessment 3
**Target length:** 250 words ±10%

---

## Presenter

| Presenter | Slides | Content | Approx. time |
|---|---|---|---|
| **Dhayanand M B** | 1–12 | Title · Problem · Dataset · Preprocessing · Architecture · Training · Results · Error analysis · Live demo · Ethics · Future work · Summary | ~13.5 min |

For speaker notes and suggested wording per slide — work from `docs/assessment-files/presentation-outline.md`.

---

## Dhayanand M B

### Student Details

- **Name:** Dhayanand M B
- **University:** RV University
- **Email:** mbdhayanand.bsc23@rvu.edu.in
- **GitHub:** https://github.com/dhayanand458
- **LinkedIn:** https://www.linkedin.com/in/m-b-dhayanand
- **Slides presented:** 1–12
- **Project:** Individual

### Contribution Table

| Author | Main Contribution | % |
|---|---|---:|
| Dhayanand M B | Full technical implementation, models, app, tests, documentation, demo, and report | 100% |
| **Total** | | **100%** |

### Draft Report (~250 words)

My contribution to ReviewPulse is the full individual implementation of the sentiment-analysis pipeline — source modules, the Streamlit web app, unit tests, and project documentation.

On the data side, I built the pseudo-XML parser (`parser.py`), the preprocessing pipeline with negation expansion (`preprocess.py`), and the vocabulary builder and PyTorch DataLoaders (`dataset.py`). I then implemented the models: the TF-IDF + Logistic Regression baseline (`baseline.py`), the bidirectional LSTM initialised with GloVe 100-dimensional embeddings (`model.py`), and the Hugging Face DistilBERT extension (`src/model_bert.py`, `src/train_bert.py`). The training loops use Adam with gradient clipping and F1-based checkpointing. I implemented evaluation with confusion matrix and error analysis (`evaluate.py`), a unified inference API (`inference.py`), and the Streamlit web app with model selector and sample review generator (`app.py`). I also produced the presentation outline, acceptance test cases with real model outputs, and this document.

An important ethical consideration is that the Blitzer et al. (2007) dataset uses filename-derived labels rather than human raters. I audited for possible rating/text conflicts and ambiguous boundary cases and found zero ambiguous rows, but the risk remains relevant in broader sentiment classification settings. Confidence values are also uncalibrated — 98% confidence does not imply 98% accuracy — and the model generalises poorly to out-of-distribution text such as logistics reviews. Any production deployment requires human oversight and periodic label audits.

This is an individual project; I am responsible for 100% of the implementation, evaluation, application, and write-up.

### APA References

- Blitzer, J., Dredze, M., & Pereira, F. (2007). Biographies, Bollywood, Boom-boxes and Blenders: Domain adaptation for sentiment classification. In *Proceedings of the 45th Annual Meeting of the ACL* (pp. 440–447). ACL. https://aclanthology.org/P07-1056/
- Hochreiter, S., & Schmidhuber, J. (1997). Long short-term memory. *Neural Computation, 9*(8), 1735–1780. https://doi.org/10.1162/neco.1997.9.8.1735
- Devlin, J., Chang, M.-W., Lee, K., & Toutanova, K. (2019). BERT: Pre-training of deep bidirectional transformers for language understanding. In *Proceedings of NAACL-HLT 2019* (pp. 4171–4186). https://doi.org/10.18653/v1/N19-1423
- Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On the dangers of stochastic parrots: Can language models be too big? In *Proceedings of the 2021 ACM FAccT Conference* (pp. 610–623). https://doi.org/10.1145/3442188.3445922
