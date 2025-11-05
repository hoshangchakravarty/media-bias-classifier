# 🧭 Media Bias Classifier (MBC)

[![Hugging Face](https://img.shields.io/badge/🤗%20Transformers-FFAE1A?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co)
[![Streamlit](https://img.shields.io/badge/🌐%20Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![PyTorch](https://img.shields.io/badge/🔥%20PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org)
[![Dataset](https://img.shields.io/badge/Kaggle-MBIC%20Dataset-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/timospinde/mbic-a-media-bias-annotation-dataset)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

> **Detect and visualize linguistic bias in news headlines using a fine-tuned DistilBERT model — integrated with NewsAPI and an interactive Streamlit dashboard.**

---

## 📰 Overview

The **Media Bias Classifier (MBC)** identifies **linguistic bias** in short text — like news headlines, tweets, and editorials — using a fine-tuned **DistilBERT** model.  
It classifies text along a **graded spectrum** (*Biased → Slightly Biased → Mixed → Slightly Non-Biased → Non-Biased*) and visualizes results through **gauge-style charts**.

The project combines:
- 🤗 **Transformers** (DistilBERT fine-tuned on MBIC dataset)
- 🌐 **Streamlit UI** for real-time classification
- 📰 **NewsAPI** for live news analysis  
- ⚙️ **Local inference** via Apple MPS / CPU fallback

---

## ✨ Features

- 🔍 Detect **media bias** in text using transformer-based NLP  
- 📰 **Live News Feed** — fetch & classify trending headlines  
- 📊 **Gauge Visualization** — intuitive bias scale display  
- 🧠 **Detailed Model Overview** — architecture, accuracy & evaluation metrics  
- ⚡ **Local-first design** — works offline if API is unavailable  

---

## 🧩 Dataset

**Source:** [MBIC — A Media Bias Annotation Dataset](https://www.kaggle.com/datasets/timospinde/mbic-a-media-bias-annotation-dataset)  
**Authors:** Timo Spinde, Felix Hamborg, et al.  
**License:** Kaggle Dataset Terms  

| Metric | Count |
|:--|--:|
| Total Samples | 1551 |
| Train Set | 1240 |
| Test Set | 311 |
| Labels | 2 (Biased / Non-Biased) |

---

## ⚙️ Installation & Setup

1️⃣ **Clone the repository**
```bash
git clone https://github.com/yourusername/media-bias-classifier.git
cd media-bias-classifier
```

2️⃣ **(Optional) Create and activate a virtual environment**
```bash
python3 -m venv venv
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate         # Windows
```

3️⃣ **Install dependencies**
```bash
pip install -r requirements.txt
```

4️⃣ **Add your NewsAPI key**
Create a `.streamlit/secrets.toml` file in the project root:
```toml
NEWSAPI_KEY = "your_api_key_here"
```
> Get a free key from [https://newsapi.org](https://newsapi.org)

---

## 🚀 Usage

### 🧠 Train the Model
```bash
python trainbias.py
```
Fine-tunes DistilBERT on the MBIC dataset and saves it in:
```
out/distilbert-mbic-binary/best
```

### 💻 Launch the Streamlit App
```bash
streamlit run app.py
```
Access the dashboard at [http://localhost:8501](http://localhost:8501).

---

## 🧭 Application Structure

### 📰 **Live News**
Fetches the top 10 trending technology headlines and classifies each with gauge-style bias meters.

### 🧩 **Classify**
Paste any custom text or headline to analyze its bias instantly.

### 📊 **About / Results**
Displays model performance metrics, architecture summary, training configuration, and sample predictions.

---

## 📈 Model Performance

| Metric | Score |
|:--|:--|
| **Accuracy** | 73.6% |
| **F1 (Macro)** | 0.68 |
| **F1 (Weighted)** | 0.72 |

**Model:** `distilbert-base-uncased`  
**Optimizer:** AdamW  
**Learning Rate:** 2e-5  
**Epochs:** 4  
**Device:** Apple MPS (Metal GPU)  
**Frameworks:** PyTorch · Transformers · Evaluate  

---

## 📸 Screenshots

> _(Add your screenshots here for GitHub preview)_  
> ```
> /assets/screenshots/
> ├── homepage.png
> ├── classify.png
> └── about.png
> ```

---

## 🧠 Future Enhancements

- 🌍 Add multilingual bias detection (XLM-R / MiniLM)  
- 💬 Include stance & sentiment detection modules  
- 🧮 Expand dataset with larger balanced corpus  
- ☁️ Deploy to Streamlit Cloud or Hugging Face Spaces  

---

## 🧾 Citation

If you use this work or dataset, please cite:

```
Spinde, T., Hamborg, F., et al. (2020). MBIC: A Media Bias Annotation Dataset.
Kaggle. https://www.kaggle.com/datasets/timospinde/mbic-a-media-bias-annotation-dataset
```

---

## 👨‍💻 Authors

**Hoshang S. Chakravarty**  
B.Tech (Hons.) · IoT & Intelligent Systems  
Manipal University Jaipur  
📧 [hoshang.c2003@gmail.com](mailto:hoshang.c2003@gmail.com)  
🌐 [hoshang.in](https://hoshang.in)

**Bhargavi Misra**  
B.Tech · Computer Science and Engineering  
Manipal University Jaipur  
📧 [bhargavimisra@gmail.com](mailto:bhargavimisra@gmail.com)  
🌐 [github.com/bhargavi-misra](https://github.com/bhargavi-misra)

**Stuti Dixit**  
B.Tech · Computer Science and Engineering  
Manipal University Jaipur  
📧 [dixitstuti2004@gmail.com](mailto:dixitstuti2004@gmail.com)

---

## 🪪 License

This project is released under the **MIT License**.  
See the [LICENSE](LICENSE) file for more details.

---

## ⭐ Show your Support

If you found this project useful, please **star 🌟 the repository** to help others discover it!
