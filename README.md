# 📝 English Sentence Grammar & Spelling Project with Adversarial NLP

## 🚀 Project Overview
This repository contains two related tasks:

1. **Grammar & Spelling Checker (Task A)**  
   - Build a classifier that determines whether an English sentence is grammatically and orthographically correct.

2. **Adversarial NLP Generation (Task B)**  
   - Use NLP techniques to transform correct sentences into incorrect ones **specifically to challenge and degrade the performance of the checker from Task A**.

Although the tasks are distinct in implementation, Task B is explicitly designed as an adversarial attack against Task A to evaluate the classifier’s robustness.

---

## 📚 Dataset
- **Size:** 1,000,000 sentence pairs  
  - Each pair contains a correct sentence ✅ and a corresponding incorrect sentence ❌  
- **Usage:**  
  - Task A uses labeled pairs for training and evaluation of the checker.  
  - Task B uses correct sentences (and optionally incorrect pairs) as inputs to generate adversarial incorrect sentences.

---

## 🤖 Task A — Grammar & Spelling Checker
- **Approach:** Traditional supervised learning using a Logistic Regression classifier with standard NLP preprocessing (tokenization, vectorization, feature engineering).  
- **Objective:** Binary classification — Correct vs Incorrect.  
- **Baseline Performance:** **80% accuracy** on held-out test data drawn from the original dataset.

---

## ⚔️ Task B — Adversarial NLP Generation (Attack)
- **Objective:** Create manipulated versions of grammatically correct sentences that cause the checker from Task A to misclassify them (i.e., reduce detection accuracy).  
- **Techniques Used:** Controlled token-level manipulations, targeted paraphrasing, subtle grammar or spelling perturbations, and syntactic rearrangements that preserve surface plausibility while introducing errors.  
- **Adversarial Evaluation:** Generated adversarial sentences are fed to the Task A checker to measure the drop in classification performance.  
- **Result:** The checker’s accuracy dropped from **80% → 30%** when evaluated on NLP-generated adversarial sentences.

---

## 📊 Key Findings
- A simple Logistic Regression classifier achieves reasonable accuracy on straightforward, labeled incorrect examples (80%).  
- Targeted NLP-based manipulations can substantially reduce classifier performance (down to 30%), showing that the classifier is vulnerable to adversarial or out-of-distribution error patterns.  
- Adversarial examples often exploit weaknesses in feature representations and the model’s inability to reason about deeper syntax and semantics.

---

## 🧭 Implications & Recommendations
- **Robustness Testing:** Classifiers should be stress-tested with adversarially generated errors, not only with naturally occurring mistakes.  
- **Model Improvements:** Consider stronger feature representations (contextual embeddings), richer syntactic features, or more powerful classifiers (e.g., transformer-based models) to improve resilience.  
- **Adversarial Training:** Incorporate adversarial examples into training data to increase robustness.  
- **Evaluation Metrics:** Use precision, recall, F1, and confusion matrices in addition to accuracy to better understand model failure modes.

---

## 📝 Conclusion
This project demonstrates two complementary perspectives on English sentence processing: a traditional supervised classifier for grammar and spelling detection, and an adversarial NLP pipeline that reveals substantial vulnerabilities in that classifier. The large drop in accuracy (80% → 30%) underscores the importance of adversarial robustness when deploying language-quality systems in real-world settings.
