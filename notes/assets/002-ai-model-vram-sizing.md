# AI Model VRAM Sizing

## Core Idea

VRAM requirement depends mostly on:

- Parameter count
- Quantization level
- Context size
- KV cache size

## Typical Requirements

| Model Size | Approx VRAM |
|------------|------------:|
| 3B | 2–4 GB |
| 7B | 4–8 GB |
| 8B | 6–8 GB |
| 13B | 10–14 GB |
| 30B | 20–30 GB |
| 70B | 40+ GB |

## Example

Qwen2.5-Coder-3B Q4_K_M

Observed:

- Total GPU memory ≈ 2.5 GB

Hardware:

- NVIDIA T1200
- 4 GB VRAM

Result:

Fully GPU offloaded.