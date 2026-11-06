# Gold test set v1 (frozen 2026-11-06)

**Never use for training, tuning, or model selection. Final evaluation only.**

- 326 messages: 183 unwanted (118 scam, 65 promo) and 143 legit
- Columns: text, label (1 = unwanted, 0 = legit), type (scam / promo / legit), tag, origin, has_link, max_sim_to_train
- Languages: English and Hinglish in Roman script, with a few Gujarati/Punjabi in Roman letters; roughly a third Hinglish (rough estimate)
- Origin: 17 hand-written, 309 LLM-generated or LLM-varied. This is an LLM-assisted challenge set, not real message traffic
- Covers hard cases: legit messages with links and OTP wording, scams imitating bank alerts, scam warnings, obfuscated text, SMS shorthand, promos with links
- Overlap check: highest character n-gram TF-IDF similarity to any training message is 0.76; none above 0.8
- Limitations: small, mostly LLM-written, scam links are fake look-alike domains
