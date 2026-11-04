# hinglish-scam-detector
Problem: Detect scam and phishing messages written in Hinglish (Hindi-English mixed, Roman script).
Why it’s hard: word-counting models ignore meaning, and spelling tricks, code-mixing, and scam warnings can all fool them.
Approach: fine-tune pretrained language models and compare them against classical baselines.
Success measure: F1 metric on scam class and report on precision (of messages flagged as scams, how many really were) and recall (of real scams, how many were caught)
