# Neural Conditional Random Fields (CRFs) for Named Entity Recognition

This repository implements a **Neural Conditional Random Field (CRF)** tagger for **Named Entity Recognition (NER)**, developed as part of a CSE project submission for 291E — **Advanced Statistical NLP** at UC San Diego.

It reproduces the **Viterbi decoding algorithm** used for structured sequence inference in CRF-based models, integrated with **BiLSTM encoders** for contextual representation learning.  
The core focus is the **implementation and comparison** of a baseline BiLSTM tagger and a BiLSTM+CRF model for sequence labeling on standard NER datasets.

<p align="center">
  <img src="https://github.com/keerthanap8898/Neural-CRF_NER-Tagger/blob/main/resources/viterbi-visualizer.jpg" width="500" alt="Viterbi Visualization"><br>
  <em>Example: Viterbi decoding visualized across state transitions in CRF inference.</em>
</p>


## ➤ Overview

| Component | Description |
|------------|-------------|
| **Goal** | Compare BiLSTM and BiLSTM+CRF models for Named Entity Recognition |
| **Core Algorithm** | Viterbi decoding for globally optimal sequence prediction |
| **Model** | BiLSTM encoder + CRF layer |
| **Dataset** | CoNLL-2003 Named Entity Recognition corpus |
| **Framework** | PyTorch |
| **Performance** | BiLSTM F1 ≈ 72.46 • BiLSTM+CRF F1 ≈ 73.50 |


## ➤ Repository Structure
```
Neural-CRF_NER-Tagger/
│
├── cse291_assignment2_starter_code.ipynb   # Baseline BiLSTM implementation
├── v_2.ipynb                               # BiLSTM + CRF with Viterbi decoding
├── Project2.pdf                            # Full project report (CSE 291E submission)
├── metadata.yml                            # Submission metadata
├── resources/                              # Algorithmic references and visuals
│   ├── Viterbi algorithm - Wikipedia.pdf
│   ├── viterbi-algorithm.png
│   ├── viterbi-pseudocode.png
│   └── viterbi-visualizer.jpg
└── Project2_assessment.zip.gitignore
```


## ➤ Installation

```bash
# Clone the repository
git clone https://github.com/keerthanap8898/Neural-CRF_NER-Tagger.git
cd Neural-CRF_NER-Tagger

# Create environment (Python 3.9+ recommended)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt
```


## ➤ Usage

Train and evaluate directly in Google Colab or locally: `jupyter notebook v_2.ipynb`

> The notebook contains:
> -	Implementation of BiLSTM Tagger
> -	Implementation of BiLSTM + CRF model with Viterbi decoding
> -	Comparative analysis, training curves, and F1 evaluation


## ➤ Core Algorithm: Viterbi Decoding

> ## The Viterbi Algorithm computes the most probable sequence of labels (tags) given emission and transition scores from the CRF layer.
> At each time step, it maintains dynamic programming states that recursively compute the maximum path probability and backtrack pointers to recover the optimal label sequence.

<p align="center">
  <img src="https://github.com/keerthanap8898/Neural-CRF_NER-Tagger/blob/main/resources/viterbi-algorithm.png" width="620" alt="Viterbi Algorithm Diagram"><br>
  <em>Dynamic programming flow for the Viterbi decoding process.</em>
</p>


## ➤ Related Literatures and References

### A. Wikipedia Reference & Pseudocode
> Canonical explanation of the dynamic programming approach for maximum-likelihood sequence estimation.
 -	[wikipedia.org/wiki/Viterbi_algorithm](https://en.wikipedia.org/wiki/Viterbi_algorithm)
 -	[wikipedia.org/wiki/Viterbi_algorithm#Pseudocode](https://en.wikipedia.org/wiki/Viterbi_algorithm#Pseudocode)

### B. Algorithm & Implementation
 -	[Viterbi Algorithm in Speech Enhancement and HMM](https://www.audiolabs-erlangen.de/resources/MIR/FMP/C5/C5S3_Viterbi.html)

### C. Visualizers
 -	[vocal.com/echo-cancellation/viterbi-algorithm-...-hmm](https://vocal.com/echo-cancellation/viterbi-algorithm-in-speech-enhancement-and-hmm)
 -	[frazierbutler.medium.com/intro-to-the-viterbi-algorithm...cf3](https://frazierbutler.medium.com/intro-to-the-viterbi-algorithm-8f41c3f43cf3)

<p align="center">
  <img src="https://github.com/keerthanap8898/Neural-CRF_NER-Tagger/blob/main/resources/viterbi-pseudocode.png" width="580" alt="Viterbi Pseudocode"><br>
  <em>Initialization, recursion, and termination stages of the Viterbi decoding process.</em>
</p>


## ➤ Results Summary

Model	F1 Score	Observations
```
BiLSTM Tagger	72.46	Accuracy drops after epoch 10; mild overfitting after epoch 3
BiLSTM + CRF	73.50	Stable learning after epoch 7; improved consistency via transition modeling
```

These results demonstrate the added stability and grammatical awareness of CRF-based decoding compared to token-independent LSTM tagging.


## ➤ References
1.	Viterbi Algorithm — Wikipedia
2.	Huang, Zhiheng et al. Bidirectional LSTM-CRF Models for Sequence Tagging. arXiv:1508.01991 (2015)
3.	Lafferty, McCallum, & Pereira (2001) — Conditional Random Fields: Probabilistic Models for Segmenting and Labeling Sequence Data.
4.	Lample, Ballesteros, Kawakami, & Dyer (2016) — Neural Architectures for Named Entity Recognition.
5.	UC San Diego — CSE 291E: Advanced Statistical NLP.


## ➤ Author

Keerthana Purushotham
Graduate Coursework — Advanced Statistical NLP (CSE 291E)
LinkedIn : [linkedin.com/in/keerthanapurushotham](linkedin.com/in/keerthanapurushotham) 


## ➤ License

This repository is released under the MIT License.
All figures and documents are provided for educational and academic use.


## ➤ Learning Value

This project demonstrates:
-	Integration of neural sequence encoders with structured probabilistic decoders
-	Application of dynamic programming via Viterbi for sequence tagging
-	Comparative evaluation between neural-only and neural-structured approaches

It serves as a clear, reproducible reference for understanding how BiLSTM-CRF architectures achieve global sequence consistency and correctness in NLP tasks.

<p align="center">
  <em>“Structured learning meets sequence modeling — decoding meaning through structure.”</em>
</p>
