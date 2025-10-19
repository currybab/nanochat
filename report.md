# nanochat training report

Generated: 2025-10-19 01:16:07

## Environment

### Git Information
- Branch: master
- Commit: dd6ff9a (dirty)
- Message: fix bug in fallback case of find_largest_model

### Hardware
- Platform: Linux
- CPUs: 8 cores (16 logical)
- Memory: 60.4 GB
- GPUs: 1x NVIDIA GeForce RTX 5090
- GPU Memory: 31.4 GB total
- CUDA Version: 12.8
- Hourly Rate: $2.00/hour

### Software
- Python: 3.10.18
- PyTorch: 2.8.0+cu128


### Bloat
- Characters: 339,272
- Lines: 8,452
- Files: 45
- Tokens (approx): 84,818
- Dependencies (uv.lock lines): 2,004

Run started: 2025-10-14 23:29:29

---

## Tokenizer training
timestamp: 2025-10-14 23:29:58

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 65,536
- train_time: 26.8675
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.9151
- token_bytes_std: 2.8736


## Tokenizer evaluation
timestamp: 2025-10-14 23:30:00

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 375 | 4.85 | +7.2% |
| korean | 893 | 745 | 1.20 | 721 | 1.24 | +3.2% |
| code | 1259 | 576 | 2.19 | 493 | 2.55 | +14.4% |
| math | 1834 | 936 | 1.96 | 966 | 1.90 | -3.2% |
| science | 1112 | 260 | 4.28 | 225 | 4.94 | +13.5% |
| fwe-train | 4208518 | 900364 | 4.67 | 856901 | 4.91 | +4.8% |
| fwe-val | 4908443 | 1059062 | 4.63 | 1010356 | 4.86 | +4.6% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 375 | 4.85 | +3.1% |
| korean | 893 | 364 | 2.45 | 721 | 1.24 | -98.1% |
| code | 1259 | 309 | 4.07 | 493 | 2.55 | -59.5% |
| math | 1834 | 832 | 2.20 | 966 | 1.90 | -16.1% |
| science | 1112 | 249 | 4.47 | 225 | 4.94 | +9.6% |
| fwe-train | 4208518 | 874799 | 4.81 | 856901 | 4.91 | +2.0% |
| fwe-val | 4908443 | 1029691 | 4.77 | 1010356 | 4.86 | +1.9% |


## Base model training
timestamp: 2025-10-17 19:11:52

- run: rtx5090-bs-8
- depth: 20
- max_seq_len: 2048
- num_iterations: -1
- target_flops: -1.0000
- target_param_data_ratio: 20
- device_batch_size: 8
- total_batch_size: 524,288
- embedding_lr: 0.2000
- unembedding_lr: 0.0040
- weight_decay: 0.0000
- matrix_lr: 0.0200
- grad_clip: 1.0000
- eval_every: 250
- eval_tokens: 10,485,760
- core_metric_every: 2000
- core_metric_max_per_task: 500
- sample_every: 2000
- model_tag: 
- Number of parameters: 560,988,160
- Number of FLOPs per token: 3.491758e+09
- Calculated number of iterations: 21,400
- Number of training tokens: 11,219,763,200
- Tokens : Params ratio: 20.0000
- DDP world size: 1
- warmup_ratio: 0.0000
- warmdown_ratio: 0.2000
- final_lr_frac: 0.0000
- Minimum validation bpb: 0.8160
- Final validation bpb: 0.8160
- CORE metric estimate: 0.2184
- MFU %: 16.85%
- Total training flops: 3.917670e+19
- Total training time: 3917.84m
- Peak memory usage: 29596.27MiB


## Base model evaluation
timestamp: 2025-10-17 19:43:29

- Model: base_model (step 21400)
- CORE metric: 0.2108
- hellaswag_zeroshot: 0.2635
- jeopardy: 0.0619
- bigbench_qa_wikidata: 0.5018
- arc_easy: 0.5157
- arc_challenge: 0.1251
- copa: 0.3000
- commonsense_qa: 0.2353
- piqa: 0.3602
- openbook_qa: 0.1173
- lambada_openai: 0.3813
- hellaswag: 0.2632
- winograd: 0.3187
- winogrande: 0.0766
- bigbench_dyck_languages: 0.0850
- agi_eval_lsat_ar: 0.0543
- bigbench_cs_algorithms: 0.3485
- bigbench_operators: 0.1333
- bigbench_repeat_copy_logic: 0.0000
- squad: 0.2409
- coqa: 0.1965
- boolq: -0.1210
- bigbench_language_identification: 0.1793


## Midtraining
timestamp: 2025-10-17 22:14:58

- run: rtx5090-bs-8
- dtype: bfloat16
- max_seq_len: 2048
- device_batch_size: 8
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- init_lr_frac: 1.0000
- weight_decay: 0.0000
- final_lr_frac: 0.0000
- eval_every: 150
- eval_tokens: 10,485,760
- total_batch_size: 524,288
- Number of iterations: 771
- DDP world size: 1
- Minimum validation bpb: 0.4190


## Chat evaluation mid
timestamp: 2025-10-17 22:40:28

- source: mid
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- ARC-Easy: 0.2803
- ARC-Challenge: 0.2713
- MMLU: 0.2898
- GSM8K: 0.0243
- HumanEval: 0.0488
- ChatCORE metric: 0.0390


## Chat SFT
timestamp: 2025-10-18 23:47:52

- run: rtx5090-bs-8
- source: mid
- dtype: bfloat16
- device_batch_size: 2
- num_epochs: 1
- max_iterations: -1
- target_examples_per_step: 32
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- weight_decay: 0.0000
- init_lr_frac: 0.0200
- eval_every: 100
- eval_steps: 100
- eval_metrics_every: 200
- Training rows: 20,843
- Number of iterations: 651
- Training loss: 1.1300
- Validation loss: 1.0824


## Chat evaluation sft
timestamp: 2025-10-19 00:12:11

- source: sft
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- ARC-Easy: 0.3178
- ARC-Challenge: 0.2713
- MMLU: 0.2837
- GSM8K: 0.0379
- HumanEval: 0.0549
- ChatCORE metric: 0.0513


## Chat RL
timestamp: 2025-10-19 15:14:29

- run: rtx5090-bs-8
- source: sft
- dtype: bfloat16
- device_batch_size: 1
- examples_per_step: 16
- num_samples: 16
- max_new_tokens: 256
- temperature: 1.0000
- top_k: 50
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- weight_decay: 0.0000
- init_lr_frac: 0.0500
- num_epochs: 1
- save_every: 60
- eval_every: 60
- eval_examples: 400


## Chat evaluation rl
timestamp: 2025-10-19 15:21:42

- source: rl
- task_name: GSM8K
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- GSM8K: 0.0652


## Summary

- Characters: 339,272
- Lines: 8,452
- Files: 45
- Tokens (approx): 84,818
- Dependencies (uv.lock lines): 2,004

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| CORE            | 0.2108   | -        | -        | -        |
| ARC-Challenge   | -        | 0.2713   | 0.2713   | -        |
| ARC-Easy        | -        | 0.2803   | 0.3178   | -        |
| GSM8K           | -        | 0.0243   | 0.0379   | 0.0652   |
| HumanEval       | -        | 0.0488   | 0.0549   | -        |
| MMLU            | -        | 0.2898   | 0.2837   | -        |
| ChatCORE        | -        | 0.0390   | 0.0513   | -        |

Total wall clock time: 71h56m+
