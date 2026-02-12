# Designing-an-LLM-Based-Application-for-Collaborative-Learning

Directory structure:
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
Installing Dependencies: 

```
pip install langchain langchain-community langchain-core langchain-text-splitters faiss-cpu langchain-ollama pypdf
```

Installing Required System Dependencies (zstd) for Ollama
Before installing Ollama, we install the `zstd` (Zstandard) compression utility.
Ollama distributes its binaries in compressed format, and `zstd` is required to properly extract and install those files in the Colab environment.
```
!sudo apt-get update
!sudo apt-get install -y zstd
```
Install Ollama from Official Installation Script
```
!curl -fsSL https://ollama.com/install.sh | sh
```
Start Ollama Server in Background Mode
We start the Ollama server using `nohup` so that it continues
running in the background even after the cell execution completes.
All logs are redirected to `ollama.log` for monitoring and debugging.
```
!nohup ollama serve > ollama.log 2>&1 &
```
