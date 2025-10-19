# nanochat training report

Generated: 2025-10-18 23:25:42

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
- Characters: 336,032
- Lines: 8,292
- Files: 43
- Tokens (approx): 84,008
- Dependencies (uv.lock lines): 2,004

Run started: 2025-10-18 23:25:42

---

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


## Summary

- Characters: 336,032
- Lines: 8,292
- Files: 43
- Tokens (approx): 84,008
- Dependencies (uv.lock lines): 2,004

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| ARC-Challenge   | -        | -        | 0.2713   | -        |
| ARC-Easy        | -        | -        | 0.3178   | -        |
| GSM8K           | -        | -        | 0.0379   | -        |
| HumanEval       | -        | -        | 0.0549   | -        |
| MMLU            | -        | -        | 0.2837   | -        |
| ChatCORE        | -        | -        | 0.0513   | -        |

Total wall clock time: 0h46m
