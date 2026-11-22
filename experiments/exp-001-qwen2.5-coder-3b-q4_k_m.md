# Experiment 001

## Date

2026-11-22

## Objective

Initial validation of local model serving.

## Runtime

```powershell
llama.exe serve -hf bartowski/Qwen2.5-Coder-3B-Instruct-GGUF:Q4_K_M
```

## Model

- Qwen2.5-Coder-3B-Instruct
- Publisher: bartowski
- Format: GGUF
- Quantization: Q4_K_M

## Hardware

### CPU

- Intel Core i7-11850H

### GPU

- NVIDIA T1200 Laptop GPU
- 4 GB VRAM

### RAM

- 32 GB

## Status

- Model loaded successfully.
- Serving process running.

## Metrics

### VRAM Usage

Observed:

```text
2551 MiB / 4096 MiB
```

### Tokens/sec

Not measured yet.

### Context Size

Unknown.

## Notes

Model fits within available 4 GB VRAM.
System remains operational while model is loaded.