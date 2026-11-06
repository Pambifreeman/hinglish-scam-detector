# Baseline notes

- Best classical baseline: TF-IDF character n-grams + logistic regression.
  5-fold grouped CV (template families capped at 5 rows): F1 0.964 ± 0.006.
  Public test (capped): precision 0.940, recall 0.966, F1 0.953.
- Capping matters: on the same public test set, uncapped precision falls to ~0.60 because
  a few template families (recharge confirmations, train alerts) are counted hundreds of times.
- Gold v1: baselines score F1 0.75-0.76, versus 0.719 for "always flag as unwanted".
  Accuracy is 0.66-0.70 versus 0.56. F1 on the majority class is a weak headline here, so we
  also report false-alarm rate and balanced accuracy.
- Failure pattern on gold (best baseline): legit messages with links 14% correct, alarming legit 20%,
  Hinglish legit alerts 20%, transactional 30%, scam warnings 30%, obfuscated scams 56%.
  Legit messages are left alone only 51% of the time; scams are caught 81%, promos 91%.
- Interpretation: the models rely on surface cues (links, alert wording, "urgent" words) and cannot tell
  a legit alert from a scam that imitates one. Several social-engineering scams without keywords are missed.
- Caveat: gold is LLM-assisted and deliberately hard, so its false-alarm rate is a stress-test figure,
  not an expected real-world rate.
