# Fine-tuning notes

- 6 runs (HingBERT and XLM-R base, 3 seeds each), 2-3 minutes each on a T4. Validation balanced accuracy ~0.97 for all.
- Public test (capped): balanced accuracy 0.963 for both models vs 0.948 best baseline (~1.5 points).
- Gold v1: HingBERT 0.670 ± 0.009, XLM-R 0.642 ± 0.006, vs 0.676 baseline and 0.689 frozen HingBERT.
  Differences are within sampling noise (326 messages). Fine-tuning did not improve on gold.
- Public test (all rows): HingBERT seed 42 balanced accuracy 0.890, seeds 43/44 0.778: large seed variance.
- Gold tags (HingBERT seed 42): obfuscated improved 0.56 -> 0.88; legit with links fell 0.14 -> 0.05;
  Hinglish legit alerts 0.20 -> 0.07; legit overall 48% correct, scams 81%.
- Validation (same sources as training) cannot reveal these gaps: val 0.97 vs gold 0.67.
- Hypothesis: legit training messages are almost all personal chat, so models learn "link or automated wording = unwanted".
