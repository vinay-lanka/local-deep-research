# Local Duck-Duck-Go Web-Scraping using LangChain and Ollama

This repository contains the final project for the Manufacturing and Automation course. The project focuses on building a fully offline web scraper tailored for manufacturing-related research and analysis.

## Project Overview

The primary goal of this project is to create a robust, offline web scraping tool that can assist in gathering manufacturing-related data, including:

- Step-by-step manufacturing guides.
- Sustainable material options.
- Cost analyses for various manufacturing processes.

The project leverages machine learning models and prompt engineering to generate relevant search queries and process data efficiently.

## Key Components

### 1. Jupyter Notebook: `manufacturing.ipynb`
The notebook contains:
- Implementation of a fully offline web scraper.
- Integration of machine learning models for generating search queries.
- Data processing and visualization for manufacturing research.

### 2. Pre-trained Models
The project uses pre-trained models (e.g., `blip2-opt-2.7b`) to enhance query generation and data analysis capabilities. These models are stored in the `models/` directory.

### 3. Sample Image: `obj.JPG`
A sample image is included to demonstrate image-based captioning and query generation.

## Installs
```bash
# Ollama install
curl -fsSL https://ollama.com/install.sh | sh
ollama pull gemma3:4b

```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/vinay-lanka/local-deep-research.git
   cd local-deep-research

   ```
2. Install the required dependencies:
   ```bash
   conda env create -f environment.yml
   ```
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook manufacturing.ipynb
   ```