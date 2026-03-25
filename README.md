**Hybrid BERT Intrusion Detection System (IDS)**

**Paper replicated:**
["A Novel Hybrid BERT and Deep Learning Model Network Intrusion Detection System for Healthcare Electronics"](https://ieeexplore.ieee.org/document/10553415/).

The idea is to treat network traffic payloads as text and use NLP techniques (BERT + DNN) to detect malicious traffic, including zero-day attacks, in healthcare IoT environments.

**Dataset:** [ECU-IoHT](https://ro.ecu.edu.au/context/datasets/article/1051/type/native/viewcontent)

**Architecture**  
- Feature extractor: Pre-trained **BERT** model  
- Classifier: Deep Neural Network (DNN)

**Target Performance**  
- Accuracy: ~99.11%  
- Precision/Recall/F1-score: ~99%
