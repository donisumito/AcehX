# AcehX
AcehX is a high-quality Acehnese language resource designed to support NLP research,
including Masked Language Modeling (MLM) and sentiment analysis for low-resource Indonesian regional languages.

This repository contains:

- **AcehX Corpus** (unlabeled dataset)
- **AcehX Sentiment Dataset** (labeled dataset)
- **AcehX Tokenizer Vocabulary**
- **[AcehXBERT](https://huggingface.co/doniNlp/AcehXBERT-base) (MLM + Sentiment Classification Model)**

AcehXBERT is introduced in the paper:

**“Development of AcehX for Sentiment Analysis Using a BERT-Based Model” (2025)**

## 📚 Dataset Overview
### **1. AcehX Corpus for MLM**
The full AcehX corpus contains 63,367 sentences.

In this study, 41,627 sentences were used for MLM pretraining of AcehXBERT.

A large unlabeled Acehnese corpus collected from:

- literature, folklore, oral traditions  
- traditional customs and customary law texts  
- Wikipedia  
- YouTube comments  

| Dataset | Type | Sentences | 
|--------|---------|----------|
| AcehX Corpus | Unlabeled (MLM) | **41,627** |

Used for MLM pretraining of AcehXBERT.

### **2. AcehX Sentiment for Sentiment Analysis**
Manually labeled by native Acehnese speakers into:

- Positive  
- Negative  
- Neutral  

| Dataset | Type | Sentences |
|--------|---------|----------|
| AcehX Sentiment | Labeled | **3,725** |

Used for fine-tuning AcehXBERT classification model.

### **3. Distribution of sentiment dataset labels**

| Sub Dataset | Positive | Negative | Neutral | Total Sentences |
|--------|---------|----------|----------|----------|
| Training | 884 | 931 | 1,537 | 3,352 |
| Validation | 75 | 76 | 111 | 262 |
| Test | 29 | 34 | 48 | 111 |
| **Total** | **998** | **1,041** | **1,696** | **3,725** |


## Hyperparameters classification model.

| Hyperparameters | Value |
|--------|---------|
| Sequence length | 128 |
| Batch size | 8 |
| Epoch | 10 |
| Learning rate | 5e-5 |


## 🔤 AcehX Tokenizer

The IndoBERT tokenizer is extended with Acehnese vocabulary.

- Extracted vocabulary: **8,961 tokens**
- New tokens added: **4,765**
- Final vocabulary size: **35,286 tokens**

This significantly reduces OOV (out-of-vocabulary) tokens and improves Acehnese representation.


## 🧠 AcehXBERT Model

AcehXBERT is created by:

1. Extending the IndoBERT tokenizer with Acehnese tokens  
2. Pretraining with **Masked Language Modeling (MLM)** on AcehX Corpus  
3. Fine-tuning for **sentiment classification (3 classes)**  

### **Performance**

#### 📌 AcehX MLM Results
| Model | Perplexity |
|--------|----------|
| **AcehXBERT** | **78.3575** |
| NusaBERT Base | 140.7514 |
| IndoBERT Base | 76479.9258 |

#### 📌 AcehX Sentiment Results
| Model | F1-macro |
|--------|----------|
| **AcehXBERT** | **82.50%** |
| NusaBERT Base | 75.36% |
| IndoBERT Base | 73.00% |


AcehXBERT outperforms existing Indonesian and multilingual BERT models.

# Acknowledgement

The **AcehXBERT** dataset was collaboratively collected by the author and
the following contributors:

| Name | Affiliation |
|--------|----------|
| Doni Sumito Sukiswo | Universitas Syiah Kuala (USK) |
| Muhammad Ruski | Universitas Syiah Kuala (USK) |
| Habib Asy Muhyi | Universitas Syiah Kuala (USK) |
| Muttaqin | Universitas Syiah Kuala (USK) |
| Iskandar | Universitas Syiah Kuala (USK) |
| Saryulis | Universitas Syiah Kuala (USK) |
| Maria Ulfa | Universitas Syiah Kuala (USK) |
| Fadhilah Syafa | Universitas Syiah Kuala (USK) |
| Nurul Asmi Amalia | Universitas Syiah Kuala (USK) |
| Aida Afira | Universitas Syiah Kuala (USK) |
| Hafizha Dini Giandra | Universitas Syiah Kuala (USK) |

# Citation
You can find the full details in our paper:  
**[Development of AcehX for Sentiment Analysis Using a BERT-Based Model](https://)**

If you use AcehX or AcehXBERT, please cite:
```bibtex
@inproceedings{sukiswo-etal-2025-acehx,
    title     = {Development of AcehX for Sentiment Analysis Using a BERT-Based Model},
    author    = {Doni Sumito Sukiswo and Hammam Riza and Muhammad Subianto
                 and Taufik Fuadi Abidin and Afnan},
    booktitle = "Proceedings of the The 28th International Conference of Oriental COCOSDA ",
    month = november,
    year      = {2025}
}
```
