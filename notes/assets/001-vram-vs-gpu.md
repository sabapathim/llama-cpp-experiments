# VRAM vs GPU

## Analogy

GPU = Chef

VRAM = Chef's work table

RAM = Storage room

## Relationship

The GPU performs the computation.

The VRAM stores the model weights, KV cache, tensors, and intermediate data required by the GPU.

The GPU cannot efficiently process data that does not fit into its working memory.

## AI Perspective

When running an LLM:

- GPU = computation engine
- VRAM = memory that holds the model

A powerful GPU with insufficient VRAM may be unable to load a large model.

## Example

NVIDIA T1200

- VRAM: 4 GB

Qwen2.5-Coder-3B Q4_K_M

- Model Buffer: ~1835 MiB
- KV Cache: ~603 MiB
- Compute Buffers: ~97 MiB
- Total: ~2535 MiB

Result:

Model fits completely into available VRAM.