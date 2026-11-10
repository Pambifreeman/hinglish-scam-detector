# Frozen embedding notes

- HingBERT's tokenizer splits Hinglish like English BERT (1.86 pieces per word); XLM-R is more efficient (1.76).
- Frozen embeddings + logistic regression vs best TF-IDF baseline:
  public test (all rows): false-alarm rate 0.434 -> 0.178, balanced accuracy 0.768 -> 0.89;
  public test (capped): tied (~0.95); gold: balanced accuracy 0.689 (HingBERT), 0.671 (XLM-R), 0.676 (baseline).
- On gold, frozen embeddings lower false alarms (0.49 -> 0.39) but also lower scam recall (0.84 -> 0.77).
- Improved tags: has_link 0.14 -> 0.43, alarming 0.20 -> 0.55, transactional 0.30 -> 0.45.
  Unchanged: hinglish_alert 0.20, scam_warning 0.30. Hinglish scams: 0.84 -> 0.68.
- HingBERT and XLM-R are tied within noise; gold has only 326 messages.
