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

Run started: 2025-10-19 01:16:07

---

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
| GSM8K           | -        | -        | -        | 0.0652   |

Total wall clock time: unknown
