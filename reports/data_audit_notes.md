# Data audit notes

- Hinglish scam dataset (10,000 rows): only 743 unique texts (7.4%), 334 distinct lines after removing greetings. 99.4% of a random test split already appeared in training, and a TF-IDF + logistic regression model scored a perfect 1.000. Unusable for honest evaluation.
- ScamShield (85,680 rows): mostly English real SMS. About 88% of its 3,005 Hinglish rows come from synthetic or template sources.
- After a grouped split (no near-duplicate leakage): the same simple model scores 72% accuracy, F1 0.73 on the unwanted class.
- The 548 false alarms come from just 43 template families, mostly legit transactional alerts (train updates, recharge confirmations).
