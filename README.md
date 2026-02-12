# Designing an LLM-Based Application for Collaborative
Learning

## Directory structure:
``` 
    ├── README.md
    ├── arch_prompt.md
    ├── concept.md
    ├── Code
    |    └── ALMA.ipynb
    ├── Hybrid/
    │   ├── one_res.md
    │   ├── three_res.md
    │   └── two_res.md
    ├── No_RAG/
    │   └── one.md
    └── RAG/
        ├── prompt_one_res.md
        ├── prompt_three_res.md
        └── prompt_two_res.md
```
To run the project all you need is to run the cells within `Code/ALMA.ipynb`.
## 1-Installing Dependencies: 

```
pip install langchain langchain-community langchain-core langchain-text-splitters faiss-cpu langchain-ollama pypdf
```

## 2-Installing Required System Dependencies (zstd) for Ollama
Before installing Ollama, we install the `zstd` (Zstandard) compression utility.
Ollama distributes its binaries in compressed format, and `zstd` is required to properly extract and install those files in the Colab environment.
```
!sudo apt-get update
!sudo apt-get install -y zstd
```
## 3-Install Ollama from Official Installation Script
```
!curl -fsSL https://ollama.com/install.sh | sh
```
## 4-Start Ollama Server in Background Mode
We start the Ollama server using `nohup` so that it continues
running in the background even after the cell execution completes.
All logs are redirected to `ollama.log` for monitoring and debugging.
```
!nohup ollama serve > ollama.log 2>&1 &
```

## 5-Pull Ollama Model (gemma3:12b) for Applications
Downloading the `gemma3:12b` model from Ollama’s repository.
This model is used in applications and will be available locally
for inference in Colab.

```
!ollama pull gemma3:12b
```

## 6-Pull LLaMA2 Model for Ollama Embeddings
Downloading the `llama2` model, which is required to generate embeddings using Ollama. Unlike other embeddings libraries (such as Instructor or Sentence-Transformers), Ollama embeddings depend on this specific model being available locally.

```
!ollama pull llama2

```

