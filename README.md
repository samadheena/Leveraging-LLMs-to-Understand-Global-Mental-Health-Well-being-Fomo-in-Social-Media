# Leveraging-LLMs-to-Understand-Global-Mental-Health-Well-being-Fomo-in-Social-Media
Table of Content
1. Overview
2. Inference Settings
3. Datasets
4. Models
5. Results
6.Fine-tuning Hyperparamters
In this work, we present the first comprehensive evaluation of multiple LLMs, including Alpaca, Alpaca-LoRA, FLAN-T5, GPT-3.5, and GPT-4, on various mental health prediction tasks via online text data. We conduct a broad range of experiments, covering zero-shot prompting, few-shot prompting, and instruction fine-tuning. More importantly, our experiments show that instruction finetuning can significantly boost the performance of LLMs for all tasks simultaneously.
CONTRIBUTIONS
Inference Settings
Zero-shot Prompting

Few-shot Prompting
, where 
 denotes # of demonstrations

Prompt Designs
Prompt Designs
![prompt_designs](https://github.com/samadheena/Leveraging-LLMs-to-Understand-Global-Mental-Health-Well-being-Fomo-in-Social-Media/assets/159759911/c4c24224-cb57-44f5-b780-08f65100f933)
Datasets
Dreaddit
This dataset collected posts from Reddit, which contains ten subreddits in five domains (abuse, social, anxiety, PTSD, and financial).
We used this dataset for a post-level binary stress prediction (Task 1).
DepSeverity
This dataset leveraged the same posts collected in Dreaddit but with a different focus on depression.
We employed this dataset for two post-level tasks: binary depression prediction (i.e., whether a post showed at least mild depression, Task 2), and four-level depression prediction (Task 3).
SDCNL
This dataset also collected posts from Reddit, including r/SuicideWatch and r/Depression.
We employed this dataset for the post-level binary suicide ideation prediction (Task 4).
CSSRS-Suicide
This dataset contains posts from 15 mental health-related subreddits.
We leveraged this dataset for two user-level tasks: binary suicide risk prediction (i.e., whether a user showed at least a suicide indicator, Task 5), and five-level suicide risk prediction (Task 6).


![enhanced_results](https://github.com/samadheena/Leveraging-LLMs-to-Understand-Global-Mental-Health-Well-being-Fomo-in-Social-Media/assets/159759911/f3c5a024-0399-4759-b972-55734844c35a)
Fine-tuning Hyperparamters
MentalRoBERTa (Baseline)
For each dataset, we convert the original text labels into ascending numbers starting from 0
num_train_epochs=3, per_device_train_batch_size = 4, gradient_accumulation_steps = 16, per_device_eval_batch_size= 8, learning_rate = 5e-5, warmup_steps=500, weight_decay=0.01, logging_steps = 8, fp16 = False
Mental-Alpaca
We mostly leverage the same fine-tuning hyperparameters provided here with minor changes to accomdate our computing resources
Mental-FLAN-T5
max_len=1024, target_max_len=128, per_device_train_batch_size=2, per_device_eval_batch_size=1, gradient_accumulation_steps=2, learning_rate=1e-4, num_train_epochs=2



Citation

@article{xu2023mentalllm,
      title={Mental-LLM: Leveraging Large Language Models for Mental Health Prediction via Online Text Data}, 
      author={Xuhai Xu and Bingshen Yao and Yuanzhe Dong and Saadia Gabriel and Hong Yu and James Hendler and Marzyeh Ghassemi and Anind K. Dey and Dakuo Wang},
      year={2023},
      eprint={2307.14385},
      archivePrefix={arXiv},
      primaryClass={cs.HC}
}
