# 🧠 Auto Tagging Support Tickets Using LLM

## 📌 Objective
Automatically tag customer support tickets into relevant categories using a Large Language Model (LLM). The model predicts the **top 3 most probable tags** for each ticket based on its free-text description.

---

## 📂 Dataset
We use the **Support Ticket Classification Dataset** available on **Kaggle**. This dataset contains free-text support queries labeled with categories like *Billing, Technical Issue, Account Management,* etc.

---

## ⚙️ Methodology / Approach
1. **Dataset Loading & Preprocessing**  
   - Use Kaggle API to download dataset (`kaggle.json` file required).  
   - Clean, preprocess, and tokenize text.

2. **Model Development**  
   - **Zero-shot Classification:** Using a pre-trained LLM (like `facebook/bart-large-mnli`) directly to classify unseen data.
   - **Few-shot Learning:** Providing a few labeled examples in the prompt to improve accuracy.
   - **Fine-tuning (Optional):** Fine-tune the model on our labeled dataset for better performance.

3. **Evaluation Metrics**  
   - Accuracy  
   - F1-Score  
   - Precision & Recall  
   - Top-3 Accuracy (if applicable)

4. **Output**  
   - The model outputs **top 3 predicted tags** for each ticket, ranked by probability.

---

## 📊 Key Results / Observations
- Zero-shot LLMs perform decently without training but may misclassify niche categories.  
- Few-shot prompting improves category precision significantly.  
- Fine-tuned models offer the best accuracy but require GPU resources and labeled data.

---

## 🧩 Project Structure
```
📦 AutoTagging-LLM
 ┣ 📜 AutoTagging_LLM.ipynb   # Main Jupyter notebook
 ┣ 📄 README.md               # Project documentation
 ┣ 📂 data/                   # Dataset (downloaded from Kaggle)
 ┗ 📂 results/                # Output predictions & metrics
```

---

## 🚀 Setup & Usage

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/AutoTagging-LLM.git
cd AutoTagging-LLM
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
(If `requirements.txt` isn’t provided, install core packages manually:)
```bash
pip install transformers torch pandas scikit-learn matplotlib kaggle
```

### 3️⃣ Configure Kaggle API
- Go to your [Kaggle Account Settings](https://www.kaggle.com/account).
- Create a **new API token** — it will download as `kaggle.json`.
- In the Jupyter Notebook, you’ll be prompted to **upload your `kaggle.json`** automatically.

### 4️⃣ Run the Notebook
Open `AutoTagging_LLM.ipynb` in Jupyter and execute all cells sequentially.

---

## 📈 Future Improvements
- Deploy model via an API endpoint or Streamlit dashboard.
- Add unsupervised topic modeling for tag discovery.
- Experiment with more advanced LLMs (Gemma, Mistral, Claude, etc.).

---

## 👨‍💻 Author
Developed by **Wasea**, Mechanical Engineering student at **NUST EME**, passionate about AI applications in automation and text intelligence.
