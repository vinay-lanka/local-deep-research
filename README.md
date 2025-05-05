# Vision to Manufacture: A Fully Local Manufacturing Deep Research Engine

This project aims to develop a robust, self-contained system for manufacturing knowledge retrieval and analysis, designed to operate entirely locally. Drawing inspiration from deep semantic search capabilities such as those found in ChatGPT Deep Research, the system is specifically tailored to extract, organize, and synthesize manufacturing-related information with a high degree of relevance and contextual understanding.

## Project Overview
The system is intended to support manufacturing engineers, product developers, and sustainability analysts by automating the discovery and structuring of technical content. Its primary functions include:
- Detailed, step-by-step manufacturing process documentation
- Identification of sustainable and alternative material options
- Comparative cost analysis across manufacturing methods

## Technical Approach
At the core of the system is a vision-to-query pipeline. The process begins with an image input, from which the system identifies the object to be manufactured using a pretrained vision-language model (`gemma3:4b`). Based on the classification, it generates manufacturing-relevant search queries and gathers corresponding data through a custom web scraping engine. Retrieved content is embedded into a local semantic vector store for efficient retrieval.

In parallel, the system uses a static vector base built from curated course materials and technical references. This hybrid retrieval approach, combining dynamic and static sources, ensures 
broader coverage and relevance. 
The combined knowledge base is accessed through a Retrieval-Augmented Generation (RAG) framework. LangChain handles query generation, prompt orchestration, and reasoning, while ChromaDB
 powers scalable semantic search.

The final output is a comprehensive, professional-grade manufacturing report that outlines how to fabricate the identified object. This report encompasses manufacturing methods, required materials, sustainability metrics, cost considerations, and performance trade-offs, thereby serving as a domain-specific decision-support artifact.

The system architecture and pipeline is    illustrated in the following diagram:
<p align="center">
  <img src="imgs/project_pipeline.jpeg" alt="Pipeline" width="600">
</p>


## Repository Overview

### 1. Jupyter Notebook: `manufacturing.ipynb`
The notebook contains:
- Implementation of a web scraper for a dynamic database generation.
- PDF parser for a static database generation, stored using Chroma
- Integration of LLMs for generating search queries.
- A RAG based framework, to query the static and dynamic databases for manufacturing research.

### 2. Pre-trained Models
The project uses pre-trained models (`gemma3:4b`) to enhance query generation and data analysis capabilities. However the model can be changed as per convenience.

### 3. Sample Images and Outputs
A set of sample images (`/imgs`) and outputs (`/sample_outputs`) are included to demonstrate image-based captioning and query generation.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/vinay-lanka/local-deep-research.git
   cd local-deep-research
   ```

2. Install the required dependencies:
   ```bash
   conda env create -f environment.yml

   # Ollama install
   curl -fsSL https://ollama.com/install.sh | sh
   ollama pull gemma3:4b
   ```
   
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook manufacturing.ipynb
   ```