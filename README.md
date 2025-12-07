# 🚀 CrediCheck: Multilingual Fake News Verification System
**An Explainable Fake News Detection Framework using RAG, Cross-Encoder Re-ranking, and NLI-based Stance Classification**

CrediCheck is a multilingual, evidence-driven verification system that retrieves real fact-checking evidence and uses AI reasoning to determine whether a claim is **True**, **False**, **Partially True**, or **Unverified**.  
It is designed for multilingual environments and offers high accuracy along with human-readable explanations.

---

## 🔥 Key Features

### ✅ Multilingual Support  
- Detects input language automatically  
- Translates claims to English  
- Returns explanations in user’s original language  

### ✅ Evidence-Based Verification  
Uses a 3-step intelligent pipeline:  
1. **FAISS** for fast semantic retrieval  
2. **Cross-Encoder** for precision re-ranking  
3. **NLI** for stance classification (supports / contradicts / neutral)

### ✅ Explainable Output  
The system outputs:  
- Final label  
- Evidence sentences  
- Stance reasoning  
- Confidence scores  

### ✅ Fast & Scalable  
- MPNet embeddings  
- FAISS ANN search  
- Avg latency: **< 1 second**

---

# 📊 Models Used

### **1. Sentence Embedding Model**
- `sentence-transformers/all-mpnet-base-v2`

### **2. Cross-Encoder for Evidence Re-ranking**
- `cross-encoder/ms-marco-MiniLM-L-6-v2`

### **3. NLI Stance Classification Model**
- `cross-encoder/nli-deberta-v3-base`

---

# ⚙️ How It Works

### **1️⃣ Language Processing**
- Detect claim language  
- Translate into English  

### **2️⃣ Semantic Embedding using MPNet**
- Claim is converted into a 768-dim vector  
- Evidence database already stored as vectors  

### **3️⃣ Evidence Retrieval with FAISS**
- Fast Approximate Nearest Neighbour (ANN) search  
- Retrieves Top-K candidates  

### **4️⃣ Cross-Encoder Re-ranking**
- Reads claim + evidence together  
- Produces highly accurate relevance scores  

### **5️⃣ NLI Stance Classification**
Determines whether evidence:  
- Supports  
- Contradicts  
- Neutral  

### **6️⃣ Result Aggregation**
Final label based on evidence stance.

---

# 🛠️ Installation

```bash
git clone [https://github.com/<your-repo>/credicheck.git](https://github.com/Roxx23/Credickeck---Multilingual-Fake-News-Detection.git)
cd credicheck

pip install -r requirements.txt
