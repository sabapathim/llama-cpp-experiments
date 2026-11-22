# Experiment 002

## Date

2026-11-22

## Objective

Measure baseline inference performance for Qwen2.5-Coder-3B-Instruct on NVIDIA T1200 4 GB GPU.

## Command

```powershell
llama cli -hf bartowski/Qwen2.5-Coder-3B-Instruct-GGUF:Q4_K_M --perf --show-timings --single-turn -p "Write a Python function that calculates factorial recursively." -n 200
```

## Model

- Qwen2.5-Coder-3B-Instruct
- GGUF
- Q4_K_M

## Hardware

### CPU

- Intel Core i7-11850H

### GPU

- NVIDIA T1200 Laptop GPU
- 4 GB VRAM

### RAM

- 32 GB

## Result

### Prompt

Write a Python function that calculates factorial recursively.

### Generated Response

Model successfully generated a valid recursive factorial implementation.

### Throughput

- Prompt Processing: 25.6 tokens/s
- Generation: 32.0 tokens/s

## Model Load Status

- Loaded successfully
- Interactive mode operational

## Notes

- Model fits comfortably within 4 GB VRAM.
- Cached model appears to be used after initial startup.
- Suitable for coding assistance and experimentation on T1200 hardware.