# LLMs can tell if you're wearing a helmet

A simple API demo using Together AI's DeepSeek-V3 model to classify helmet status from emergency department narratives. This proof-of-concept implementation, written mostly by Claude 3.7 Sonnet, achieves 98.75% match with human labels. The mismatched cases are all ambiguous narrative reports, and can be found in [data/mismatches_table.tex](data/mismatches_table.tex).

This is mainly used as a retort for the study ["Use of Generative AI to Identify Helmet Status Among Patients With Micromobility-Related Injuries From Unstructured Clinical Notes"](https://pubmed.ncbi.nlm.nih.gov/39136946/). 

Our retort is also available here:
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5247962

## Overview

This project uses the DeepSeek-V3 served by Together AI to analyze emergency department narratives and classify helmet status:
- 1: Helmet worn
- 0: No helmet worn 
- 2: Cannot be determined from narrative

## Setup

1. Clone this repository
2. Create an `api.env` file with your Together AI API key:
   ```
   TOGETHER_API_KEY=your_api_key_here
   ```
3. Install the required packages:
   ```
   pip install pandas numpy tqdm python-dotenv together
   ```

## Usage

Run the Jupyter notebook `script.ipynb` to process the dataset and evaluate model performance.

The notebook:
- Loads narratives from `data/ground_truth_df.csv`
- Prompts the DeepSeek-V3 model to determine helmet status
- Compares model predictions with human annotations
- Calculates accuracy metrics

## Data

The dataset contains emergency department narratives with human-annotated helmet status.
