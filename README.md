# Zef-CNP

Code for Zero-Shot and Efficient Clarification Need Prediction in Conversational Search

In our work, we propose a zero-shot and efficient CNP framework (Zef-CNP), leveraging LLMs to genrate synthetic data and fine-tuning Pre-trained models (e.g., BERT) on generated data. 

Specifically, it contains 3 stages:

1. Zero-shot specific/ambiguous query generation with TIQ-CoT and CoQu
   
   TIQ-CoT: A topic-, information-need- and query-aware CoT prompting strategy.

   CoQu: Counterfactual query generation.
  
2. Fine-tuning an efficient CNP model
   
3. Applying the fine-tuned efficient CNP model for inference

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
Run the file 'CoT_query_generation.ipynb' to generate data with proposed TIQ-CoT and CoQu.

In the file, 

    run 'gpt_generation_topic_in' function to generate data using gpt-4o-mini.

    run 'llama3_topic_generation' function to generate data using Llama-3.1-8B-Instruct.

Run the file 'direct_query_generation.ipynb' to directly ask LLMs to genrate data. (Without TIQ-CoT and CoQu)

    run 'gpt_generation_specific_query', 'gpt_generation_vague_query' functions to generate data using gpt-4o-mini.

    run 'llama3_specific_query', 'llama3_vague_query' functions to generate data using Llama-3.1-8B-Instruct.


## How to fine-tuning

Use the generated data and Run the file 'fine_tuning_and_inference.ipynb'

## The format of generated data

Two attributes: 'initial_request' and 'bianry_label'

Number of specific queries: 2.5k

Number of ambiguous queries: 2.5k

