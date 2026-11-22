# VRAM Formula

## Basic Formula

VRAM ≈ Parameters × Bytes Per Parameter

## Common Formats

| Format | Bytes Per Parameter |
|----------|-------------------:|
| FP32 | 4 |
| FP16 | 2 |
| INT8 | 1 |
| INT4 | 0.5 |

## Example

8B Model (FP16)

8 billion × 2 bytes

≈ 16 GB

## Example

8B Model (INT4)

8 billion × 0.5 bytes

≈ 4 GB

## Practical Formula

Total VRAM ≈

Model Weights
+
KV Cache
+
Compute Buffers

## Real Example

Qwen2.5-Coder-3B Q4_K_M

Observed:

- Model Buffer: 1834.82 MiB
- KV Cache: 603.00 MiB
- Compute Buffers: 97.26 MiB

Total:

≈ 2535 MiB