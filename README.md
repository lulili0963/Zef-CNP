# Zef-CNP

Code for Zero-Shot and Efficient Clarification Need Prediction in Conversational Search

In our work, we propose a zero-shot and efficient CNP framework (Zef-CNP), leveraging LLMs to genrate synthetic data and fine-tuning Pre-trained models (e.g., BERT) on generated data. 

![FIG_ECIR_UP_16oct](https://github.com/user-attachments/assets/0224e428-d863-4561-9b8c-5ad87cb8f47c)

## How to generate
Set the huggingface token first if leveraging LLMs from huggingface.
```
!huggingface-cli login --token "..."
```
Set the OpenAI key.
```
OpenAI(api_key = "...")
```
Run the file 'CoT_query_generation.ipynb' to generate data with our proposed instructions.

Run the file 'direct_query_generation.ipynb' to directly ask LLMs to genrate data. (Without TIQ-CoT and CoQu)

## How to fine-tuning

Use the generated data and Run the file 'fine_tuning_and_inference.ipynb'
