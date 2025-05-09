# GPT-Helmet

A project to evaluate language model performance in detecting helmet status from medical narratives. This tool analyzes patient injury narratives to determine if the person was wearing a helmet during bicycle/scooter accidents.

## Overview

This project uses the DeepSeek-V3 model from Together AI to analyze emergency department narratives and classify helmet status:
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

