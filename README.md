
# 🧬 Gene-Disease Biomedical QA System

This project is a **biomedical question-answering system** that allows users to query gene-disease relationships with natural language prompts. It combines document ingestion, vector-based retrieval, and LLM-powered generation using **Mistral 7B** to produce accurate, context-based responses.

---

## 🔧 Features

- **🧠 LLM-Powered QA:** Uses the [Mistral 7B Instruct](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3) model for intelligent, contextual response generation.
- **🔍 Contextual Retrieval:** Employs **FAISS** to retrieve relevant chunks of biomedical knowledge based on user queries.
- **📄 Document Ingestion:** Ingests multiple domain-specific biomedical datasets such as ClinVar, OMIM, GAD, HPO, and more.
- **🔗 Chain-of-Thought Pipeline:** Integrates retrieval, custom prompt formatting, and response generation for interpretable, accurate answers.

---

## 📁 Datasets Used

The following datasets are used as part of the knowledge base:

- `clinvar_drop.xlsx`
- `curated_grouped.xlsx`
- `gad_disease_desc.xlsx`
- `hpo_disease_sort_desc.xlsx`
- `omim_disease_desc.xlsx`

Each dataset is converted into structured `Document` objects for embedding and storage in the FAISS vector database.

---

## 🧱 Tech Stack

- **LangChain** for building retrieval-augmented QA pipelines.
- **Hugging Face Transformers** for model loading and inference.
- **FAISS** for fast vector similarity search.
- **SentenceTransformers** for embedding biomedical documents.
- **Mistral 7B** for LLM-based natural language generation.
- **Google Colab** for development and testing.

---

## 🚀 How It Works

1. **Data Preprocessing:** Excel sheets are parsed and converted into structured text-based documents.
2. **Embedding Generation:** Text is embedded using the `all-MiniLM-L6-v2` model.
3. **Vector Storage:** Embeddings are stored in a FAISS index for fast retrieval.
4. **Custom Prompting:** A custom prompt template guides the model on how to interpret gene- or disease-based queries.
5. **LLM Response:** The Mistral model generates factual responses grounded in the retrieved documents.

---

## 🧪 Example Queries

- `"Hepatitis C virus"`  
  → Returns associated genes like CCR5, IL21R, IFNL3 with OMIM IDs and descriptions.

- `"DHTKD1"`  
  → Returns related diseases such as Amino Acid Metabolic Disorder and Charcot-Marie-Tooth, with gene locations and OMIM entries.

- `"severe t lymphocytopenia"`  
  → Returns linked genes and detailed disease descriptions with relevant identifiers.

---

## 🛠 Setup Instructions

1. Clone this repo.
2. Upload required Excel files to your working directory or Colab environment.
3. Install dependencies:
   ```bash
   pip install langchain transformers sentence-transformers faiss-cpu safetensors
   ```
4. Load and run the notebook or script.

---

## 📌 Notes

- Authentication with Hugging Face Hub is optional but recommended for smoother model loading.
- This system is optimized for **biomedical QA**, but can be extended to other domains with new data.

