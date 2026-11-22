# llama.cpp Experiments

## Environment

### Operating System

- Windows 11 Enterprise
- Version 10.0.26100
- Build 26100

### CPU

- Intel Core i7-11850H

### Memory

- 32 GB RAM

### GPU

- NVIDIA T1200 Laptop GPU
- 4 GB VRAM

### Runtime

- llama.exe
- Version: 1.0.0-dev
- Build: 12375
- Commit: 9d25e0014

---

## Verified Model

### Qwen2.5-Coder-3B-Instruct

- Source: bartowski/Qwen2.5-Coder-3B-Instruct-GGUF
- Quantization: Q4_K_M
- Format: GGUF

### GPU Offload

- 37/37 layers offloaded
- Output layer offloaded
- 35 repeating layers offloaded
- Entire model runs on GPU

### Backend

- Vulkan backend
- Device: Vulkan1

### Memory Usage

| Component | Size |
|------------|---------:|
| Model Buffer | 1834.82 MiB |
| KV Cache | 603.00 MiB |
| Compute Buffer | 97.26 MiB |
| Total GPU Usage | ~2535 MiB |

---

## Benchmark Results

| Experiment | Model | Quant | Prompt t/s | Generation t/s |
|------------|--------|--------|-----------:|---------------:|
| EXP-002 | Qwen2.5-Coder-3B-Instruct | Q4_K_M | 25.6 | 32.0 |

---

## Experiments

### EXP-001

Model loading validation.

File:

```text
experiments/exp-001-qwen2.5-coder-3b-q4_k_m.md
```

Result:

- Model loaded successfully.
- Service operational.

### EXP-002

Baseline performance benchmark.

Command:

```powershell
llama cli -hf bartowski/Qwen2.5-Coder-3B-Instruct-GGUF:Q4_K_M --perf --show-timings --single-turn -p "Write a Python function that calculates factorial recursively." -n 200
```

Results:

- Prompt Processing: 25.6 tokens/s
- Generation: 32.0 tokens/s

### EXP-003

GPU offload verification.

Command:

```powershell
llama cli -hf bartowski/Qwen2.5-Coder-3B-Instruct-GGUF:Q4_K_M --verbose --single-turn -p "hello" -n 10
```

Results:

- 37/37 layers offloaded
- Vulkan1 backend
- Model buffer: 1834.82 MiB
- KV cache: 603.00 MiB
- Compute buffer: 97.26 MiB
- Approximate GPU memory usage: 2535 MiB

---

## Hardware Capability Summary

### Verified Working Configuration

- Model: Qwen2.5-Coder-3B-Instruct
- Quantization: Q4_K_M
- Backend: Vulkan
- GPU: NVIDIA T1200 Laptop GPU
- VRAM: 4 GB

### Verified Metrics

- Fully GPU offloaded
- 37/37 layers on GPU
- ~2.5 GB VRAM consumption
- 32.0 tokens/s generation speed
- 25.6 tokens/s prompt processing

### Conclusion

Qwen2.5-Coder-3B-Instruct Q4_K_M fits completely into the 4 GB VRAM available on the NVIDIA T1200 Laptop GPU and runs with full GPU offloading through the Vulkan backend.


## Knowledge Notes

| Note | Topic |
|--------|--------|
| 001 | VRAM vs GPU |
| 002 | AI Model VRAM Sizing |
| 003 | VRAM Formulas |