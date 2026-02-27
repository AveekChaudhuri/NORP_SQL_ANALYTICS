# SQL‐Generation Prompting Experiments

This repository contains Jupyter notebooks to:

1. **Preprocess** various text→SQL datasets  
2. **Prompt** four different LLM endpoints (GPT, LLaMA, Cohere, Perplexity)  
3. **Evaluate** generated SQL using Levenshtein‐distance metrics  

---

## Requirements

- **Python 3.8+**  
- **Jupyter Notebook** or **JupyterLab**

Run the following pip install command to install all the dependencies:
<pre> pip install pandas matplotlib seaborn openai </pre>

## Data Preprocessing

1. Open and **Run All** cells in `data_preprocessing.ipynb`. You should see the following csv files in the project directory:
   - `train.csv`
   - `validation.csv`
   - `test.csv`
   - `spider_dataset.csv`
   - `spider_cleaned.csv`
  
## Prompting Notebooks

1. For each model, open the corresponding notebook:
   - `gpt-prompting.ipynb`
   - `llama-prompting.ipynb`
   - `cohere-prompting.ipynb`
   - `perplexity-prompting.ipynb`
2. For each notebook, place your associated API Key for each model in the second cell in this line:
<pre> openai.api_key = 'YOUR_API_KEY' </pre>
3. Within each notebook, **Run All**:
4. Each notebook will:
   - Load the preprocessed dataset  
   - Use its `get_sql_from_<model>(prompt, temperature, max_tokens)` function  
   - Generate SQL for each prompt  
   - Compute Levenshtein distance against ground-truth SQL  
   - View the results and metrics displayed at the last cell of each notebook 
