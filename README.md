# Designing an LLM-Based Application for Collaborative Learning

This repository presents an LLM-based application for collaborative learning in higher education. The system implements three distinct approaches to facilitate knowledge co-construction through dialogue: RAG-based, prompt-based, and hybrid methods.

## 📋 Important Note

This application was developed in **Google Colab** due to hardware constraints. Running LLM inference locally requires significant computational resources that exceed typical CPU capabilities, because: 

**My Local System Configuration:**
- CPU: 12th Gen Intel(R) Core(TM) i5-1235U (1.30 GHz)
- Issue: Local LLM inference and embeddings crash the runtime on this hardware

**Graphical UI Option:**
If a graphical user interface is required, you can use **LocalTunnel** (with Node modules npx) or **Ngrok** to redirect a public link from Colab to an external URL, since Colab does not natively support graphical user interfaces.

## 📁 Directory Structure

```
.
├── README.md
├── Sherin Thomas, Sudhanshu Passi - PyTorch Deep Learning Hands-On_ Build CNNs, RNNs, GANs, reinforcement learning, and more, quickly and easily (2019, Packt Publishing).pdf
├── arch_prompt.md
├── concept.md
├── Code/
│   └── ALMA.ipynb
├── Hybrid/
│   ├── one_res.md
│   ├── two_res.md
│   └── three_res.md
├── No_RAG/
│   └── one.md
└── RAG/
    ├── prompt_one_res.md
    ├── prompt_two_res.md
    └── prompt_three_res.md
```

## 🚀 Quick Start

To run the project, simply execute all cells in `Code/ALMA.ipynb` sequentially. The notebook contains detailed instructions for each step.
make sure that the pdf `Sherin Thomas, Sudhanshu Passi - PyTorch Deep Learning Hands-On_ Build CNNs, RNNs, GANs, reinforcement learning, and more, quickly and easily (2019, Packt Publishing).pdf` in the `content/` in Google Colab.

## 📦 Installation & Setup

Follow these steps in order within the Google Colab notebook:

### 1. Install Python Dependencies

```bash
pip install langchain langchain-community langchain-core langchain-text-splitters faiss-cpu langchain-ollama pypdf
```

### 2. Install System Dependencies (zstd)

Before installing Ollama, install the `zstd` (Zstandard) compression utility. Ollama distributes its binaries in compressed format, and `zstd` is required to properly extract and install those files in the Colab environment.

```bash
!sudo apt-get update
!sudo apt-get install -y zstd
```

### 3. Install Ollama

Download and execute the official Ollama installation script:

```bash
!curl -fsSL https://ollama.com/install.sh | sh
```

### 4. Start Ollama Server

Start the Ollama server using `nohup` so that it continues running in the background even after the cell execution completes. All logs are redirected to `ollama.log` for monitoring and debugging.

```bash
!nohup ollama serve > ollama.log 2>&1 &
```

### 5. Pull the Main LLM Model

Download the `gemma3:12b` model from Ollama's repository. This model is used for dialogue generation and will be available locally for inference in Colab.

```bash
!ollama pull gemma3:12b
```

### 6. Pull the Embeddings Model

Download the `llama2` model, which is required to generate embeddings using Ollama. Unlike other embedding libraries (such as Instructor or Sentence-Transformers), Ollama embeddings depend on this specific model being available locally.

```bash
!ollama pull llama2
```

## 💬 Using the Chatbot

After completing the setup steps above, run the cell containing the chatbot loop to start interacting with the collaborative learning system:

```python
print("\n🤝 Collaborative Partner (type 'exit' to quit)\n")

while True:
    user_query = input("You: ").strip()
    
    if user_query.lower() in {"exit", "quit"}:
        print("👋 Goodbye!")
        break
    
    response = chain.invoke({"question": user_query})
    print("\nAI:", response, "\n")
```

**To exit:** Type `exit` or `quit`

## 🎯 Project Overview

This application implements three approaches to collaborative learning:

1. **RAG (Retrieval-Augmented Generation)**: Uses semantic search on course materials (PDFs) to retrieve relevant context and guide collaborative dialogue.

2. **No RAG (Prompt-Based)**: Relies on prompt engineering and the LLM's inherent knowledge without external document retrieval.

3. **Hybrid**: Combines RAG retrieval with enhanced domain validation, treating retrieved materials as shared artifacts for collaborative reasoning.

## 📚 Additional Documentation

- `arch_prompt.md`: Architecture and prompt design details
- `concept.md`: Conceptual framework and pedagogical approach
- `Hybrid/`, `No_RAG/`, `RAG/`: Sample interaction results for each approach (prompts, results)
- `Sherin Thomas, Sudhanshu Passi - PyTorch Deep Learning Hands-On_ Build CNNs, RNNs, GANs, reinforcement learning, and more, quickly and easily (2019, Packt Publishing).pdf`: used as a course material in RAG systems.

## 🔬 Research Context

This work was developed for the **PhD Trial Task ALMA**.


## 📧 Contact
     ayoub.elkhaiari@usmba.ac.ma
---

**Note:** This is an educational tool designed to facilitate learning through dialogue, not a replacement for instructors.
