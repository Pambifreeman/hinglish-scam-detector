# Baseline notes

- Best classical baseline: TF-IDF character n-grams + logistic regression.
  5-fold grouped CV (template families capped at 5 rows): F1 0.964 ± 0.006.
  Public test (capped): precision 0.940, recall 0.966, F1 0.953.
- Capping matters: on the same public test set, uncapped precision falls to ~0.60 because
  a few template families (recharge confirmations, train alerts) are counted hundreds of times.
- Gold v1 (best baseline, TF-IDF chars + LogReg): precision 0.688, recall 0.842, F1 0.757,
  false-alarm rate 0.490, balanced accuracy 0.676. Always-flag baseline: F1 0.719, balanced accuracy 0.500.
  Word-count Naive Bayes flags 75% of legit gold messages (balanced accuracy 0.611).
- Public test (capped) balanced accuracy 0.948 vs gold 0.676: a ~27-point gap between public data and the harder gold set.
- Hinglish on public test looks fine (F1 0.95) but a large share of those rows come from template sources
  (ysangam scores 1.00); gold shows Hinglish legit alerts only 20% correct.
