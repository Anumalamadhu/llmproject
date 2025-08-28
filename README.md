# LLM SQL Fine-tuning Project

A machine learning project that fine-tunes Large Language Models (LLMs) to generate SQL queries from natural language questions.

## What This Project Does

This project trains AI models to automatically convert plain English questions into SQL database queries. For example:
- **Input**: "What is the average salary of employees in the marketing department?"
- **Output**: `SELECT AVG(salary) FROM employees WHERE department = 'marketing';`

## Models Used

The project compares two different AI models:

1. **Llama 3.2 (3B parameters)** - Fine-tuned using standard supervised learning
2. **Gemma 3.1 (1B parameters)** - Fine-tuned with reasoning capabilities using GRPO (Generalized Reward-based Policy Optimization)

## Dataset

- **Source**: Gretel AI's synthetic text-to-SQL dataset
- **Content**: Natural language questions paired with corresponding SQL queries
- **Features**: Different complexity levels and task types (SELECT, INSERT, UPDATE, etc.)

##  Key Features

- **Data Preprocessing**: Cleans SQL contexts by removing unnecessary INSERT statements
- **Model Comparison**: Evaluates both models using ROUGE scores
- **Visualization**: Charts showing training loss, data distribution, and complexity analysis
- **Inference Pipeline**: Ready-to-use functions for generating SQL from new questions

## Results

The project evaluates model performance using ROUGE metrics:
- **ROUGE-1**: Measures word overlap
- **ROUGE-2**: Measures phrase overlap  
- **ROUGE-L**: Measures longest common subsequence

## Technologies Used

- **Unsloth**: Fast LLM training and inference
- **Hugging Face**: Model hosting and datasets
- **PEFT**: Parameter-efficient fine-tuning
- **TRL**: Transformer reinforcement learning
- **PyTorch**: Deep learning framework

## Project Structure

```
├── LLM_SQL_Finetuning_.ipynb    # Main notebook with all code
├── README.md                     # This file
├── outputs/                      # Model checkpoints (generated during training)
└── sql_fintuned_10/             # Saved Llama model
└── gemma-3/                     # Saved Gemma model
```

## How to Run

1. **Install Dependencies**: Run the pip install commands in the notebook
2. **Set Up Hugging Face**: Add your Hugging Face token for model access
3. **Run Training**: Execute the notebook cells to train both models
4. **Test Models**: Use the inference sections to test with your own questions

## Example Usage

```python
# Ask a question in plain English
question = "Show me all customers from New York"
context = "CREATE TABLE customers (id INT, name VARCHAR, city VARCHAR);"

# Get SQL query from the model
sql_query = answer_question(question, context)
print(sql_query)  # Output: SELECT * FROM customers WHERE city = 'New York';
```
