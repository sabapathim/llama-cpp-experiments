# Experiment 002

## Date

2026-11-22

## Objective

Measure baseline inference performance of Qwen2.5-Coder-3B-Instruct on NVIDIA T1200 4 GB VRAM.

## Environment

### CPU

- Intel Core i7-11850H

### RAM

- 32 GB

### GPU

- NVIDIA T1200 Laptop GPU
- 4 GB VRAM

### Runtime

- llama.exe
- Version: 1.0.0-dev
- Build: 12375
- Commit: 9d25e0014

## Model

- Qwen2.5-Coder-3B-Instruct
- GGUF
- Q4_K_M

## Command

```powershell
llama cli -hf bartowski/Qwen2.5-Coder-3B-Instruct-GGUF:Q4_K_M --perf --show-timings --single-turn -p "Write a Python function that calculates factorial recursively." -n 200
```

## Prompt

```text
Write a Python function that calculates factorial recursively.
```

## Output

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n-1)

print(factorial(5))
```

## Performance

| Metric | Value |
|----------|--------:|
| Prompt Processing | 25.6 tokens/s |
| Generation | 32.0 tokens/s |

## Observations

- Model generated a valid recursive factorial implementation.
- Response quality was correct for the prompt.
- No runtime errors observed.
- Model was responsive on local hardware.

## Conclusion

Qwen2.5-Coder-3B-Instruct (Q4_K_M) achieved:

- 25.6 tokens/s prompt processing
- 32.0 tokens/s text generation

on an NVIDIA T1200 Laptop GPU with 4 GB VRAM.