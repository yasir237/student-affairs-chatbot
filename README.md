# 🤖 Student Affairs ChatBot

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LLaMA](https://img.shields.io/badge/LLaMA-Meta%20AI-blue?style=for-the-badge)
![NLP](https://img.shields.io/badge/NLP-Natural%20Language%20Processing-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Accuracy](https://img.shields.io/badge/Accuracy-92%25-success?style=for-the-badge)

**Kırıkkale University — Computer Engineering Department**
**2024–2025 Graduation Project**

</div>

---

## 📌 Overview

**Student Affairs ChatBot** is an AI-powered assistant that answers frequently asked questions directed at university student affairs offices — automatically, accurately, and 24/7.

Built on the **LLaMA** large language model architecture and fine-tuned on a custom dataset collected from Kırıkkale University's official web pages, the system understands natural Turkish language queries and responds with accurate, context-appropriate answers.

> 🎓 Developed as a **graduation project** at Kırıkkale University, Computer Engineering Department, under the supervision of **Assoc. Prof. Dr. Fahrettin HORASAN**.

---

## 👥 Team

| Role | Name |
|------|------|
| 🎓 Advisor | Assoc. Prof. Dr. Fahrettin HORASAN |
| 👨‍💻 Developer | Yasir Ayad Hamed AL RAWEE |
| 👨‍💻 Developer | Yusuf Ömer KARA |
| 👨‍💻 Developer | Mehmet Akif KAYMAK |

---

## 📊 Results

| Metric | Value | Description |
|--------|-------|-------------|
| **Accuracy** | 92% | Correct response rate in user testing |
| **Availability** | 24/7 | No staff intervention required |
| **Augmentation** | 3 methods | EDA + Back-Translation + T5 Paraphrasing |
| **Base Model** | LLaMA | Fine-tuned on custom university dataset |

---

## 🎬 Demo Video

<div align="center">

[![Demo Video](https://img.youtube.com/vi/AiV-jG-OoPs/maxresdefault.jpg)](https://www.youtube.com/watch?v=AiV-jG-OoPs)

▶️ **[Watch the full demo on YouTube](https://www.youtube.com/watch?v=AiV-jG-OoPs)**

</div>

---

## 🖼️ Screenshots

### Chat Interface


<div align="center">
  <img src="https://github.com/user-attachments/assets/d00c5293-8e15-48b0-ad78-9bc9d398cdc2" alt="ChatBot Interface — Student Query" width="80%">
  <p><em>Kırıkkale University Assistant — student asks a question and receives an instant answer</em></p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/ffbfeb17-a17e-420c-9c29-6d5bdcf80c39" alt="ChatBot Interface — Cafeteria Hours Response" width="80%">
  <p><em>Example response — cafeteria hours query answered with accurate schedule information</em></p>
</div>



### Project Poster

<div align="center">
  <img src="https://github.com/user-attachments/assets/ee1014a4-edbb-4068-a460-933c61ea83e9" alt="Project Poster — Kırıkkale University 2024-2025 Graduation Projects Exhibition" width="85%">
  <p><em>Official project poster presented at Kırıkkale University 2024–2025 Graduation Projects Exhibition</em></p>
</div>

---

## 📄 Project Presentation (PDF)

<div align="center">

📥 **[Download Full Project Presentation (PDF)](https://github.com/yasir237/student-affairs-chatbot/blob/main/chatbot-projesi.pdf)**

</div>

> The PDF contains the complete project poster including introduction, methodology, results, discussion, and references as presented at the graduation projects exhibition.

---

## 🔬 How It Works

### System Pipeline

```
University Website
        │
        ▼
┌───────────────┐
│  Web Scraping │  BeautifulSoup + Requests
│  (Data Collect)│
└──────┬────────┘
       │
       ▼
┌───────────────────────────────────┐
│        Data Augmentation          │
│  ┌─────────┐ ┌──────────────────┐ │
│  │   EDA   │ │ Back-Translation │ │
│  └─────────┘ └──────────────────┘ │
│       ┌────────────────┐          │
│       │ T5 Paraphrasing│          │
│       └────────────────┘          │
└────────────────┬──────────────────┘
                 │
                 ▼
        ┌─────────────────┐
        │  LLaMA Fine-tune│  Face FungE method
        │  (Q&A Format)   │  on augmented dataset
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │   ChatBot API   │
        └────────┬────────┘
                 │
                 ▼
        Student Interface ✅
        92% Accuracy | 24/7
```

---

## 📦 Data Augmentation

Since the scraped dataset was limited in size, three augmentation techniques were applied to expand and diversify the training data:

### 1. EDA — Easy Data Augmentation
```
Original:  "Kayıt yenileme tarihleri ne zaman?"
Augmented: "Kayıt tarihleri yenileme ne zaman?"  ← word swap
           "Kayıt ne zaman?"                      ← word deletion
           "Tescil yenileme tarihleri ne zaman?"  ← synonym replacement
```

### 2. Back-Translation
```
Turkish → English → Turkish

Original:  "Sınav sonuçları ne zaman açıklanır?"
EN:        "When will exam results be announced?"
Back-TR:   "Sınav sonuçları hangi tarihte ilan edilir?"
```

### 3. T5 Paraphrasing
```
Original:   "Burs başvurusu için hangi belgeler gerekli?"
Paraphrase: "Burs için başvururken hangi evraklar isteniyor?"
```

---

## 🧠 Model Architecture

### Base Model: LLaMA (Meta AI)
- Large language model with strong Turkish NLP capabilities
- Pre-trained on broad multilingual corpus
- Selected for its natural language understanding performance

### Fine-tuning: Face FungE Method
- Dataset structured in **question → answer** format
- Training optimized specifically for student affairs Q&A pairs
- Model learns to map natural language student queries to correct institutional answers

---

## 💬 Example Conversations

```
👤 Student: Merhaba, size nasıl yardımcı olabilirim?

🤖 Bot: Merhaba! Size nasıl yardımcı olabilirim?

---

👤 Student: kütüphane hakkında bilgi ver

🤖 Bot: Kütüphane hafta içi 08:30-19:30,
         Cumartesi 10:00-16:00 saatleri arasında açıktır.
         Pazar günü ise kapalıdır.
         Ödünç alınan kitaplar 30 TL'dir.

---

👤 Student: yemekhane saatleri verilir misin

🤖 Bot: Öğle yemeği: 11:00-14:00
         Akşam yemeği: 16:00-19:00 saatleri arasında servis edilmektedir.
         Yemek fiyatı öğrenciler için 30 TL'dir.
```

---

## ⚙️ Installation & Usage

### Requirements

```bash
pip install torch transformers beautifulsoup4 requests nlpaug
```

### Running the ChatBot

```bash
git clone https://github.com/yasir237/student-affairs-chatbot
cd student-affairs-chatbot
pip install -r requirements.txt
python app.py
```

### Data Collection (Web Scraping)

```python
from bs4 import BeautifulSoup
import requests

url = "https://ogrenciisleri.kku.edu.tr"
response = requests.get(url)
soup = BeautifulSoup(response.content, "html.parser")
# Extract Q&A content...
```

### Fine-tuning the Model

```python
# Load base LLaMA model and tokenizer
# Apply Face FungE fine-tuning on augmented Q&A dataset
# Save fine-tuned model weights
python train.py --model llama --data augmented_qa.json --epochs 10
```

---

## 🔮 Future Roadmap

- [ ] Multi-language support (Arabic, English)
- [ ] Mobile application integration
- [ ] Self-updating via user feedback loop
- [ ] API integration with university live information system
- [ ] Expanded coverage — library, cafeteria, dormitory, academic calendar
- [ ] Voice interface support

---

## 📚 References

1. Raffel et al. (2020). Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer. *JMLR*
2. Devlin et al. (2018). BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding. *NAACL*
3. Wei & Zou (2019). EDA: Easy Data Augmentation Techniques for Boosting Performance on Text Classification Tasks. *EMNLP*
4. LLaMA Model — Meta AI Research
5. BeautifulSoup Documentation — https://www.crummy.com/software/BeautifulSoup/
6. Hugging Face Transformers — https://huggingface.co/docs/transformers

---

## 📄 License

This project was developed as a graduation project at Kırıkkale University. All rights reserved.

---

<div align="center">

**Kırıkkale University — Computer Engineering Department**
**2024–2025 Graduation Project**

*Developed by Yasir Ayad Hamed AL RAWEE & Yusuf Ömer KARA & Mehmet Akif KAYMAK*
*Under the supervision of Assoc. Prof. Dr. Fahrettin HORASAN*

</div>
