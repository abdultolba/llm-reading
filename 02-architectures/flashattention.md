# FlashAttention: Fast and Memory-Efficient Exact Attention (2022)

**Authors:** Tri Dao et al.  
**Link:** https://arxiv.org/abs/2205.14135

## Why this paper matters

FlashAttention made long-context Transformers practical. It showed that the main bottleneck in attention was not arithmetic, but memory access, and that reordering the computation could dramatically reduce memory usage while computing exact attention.

This work unlocked larger batch sizes, longer context windows, and higher throughput on existing hardware, without changing the model’s behavior.

## Core ideas

### Memory-aware attention computation

Standard attention materializes large intermediate matrices, which quickly exceed GPU memory for long sequences. FlashAttention avoids storing these intermediates by computing attention in blocks and fusing operations.

The key insight is to structure computation around the GPU memory hierarchy rather than the mathematical formulation alone.

### Exact attention, not approximation

Unlike earlier methods that approximated attention to save memory, FlashAttention computes the exact same result as standard scaled dot-product attention. The improvement comes entirely from how the computation is scheduled and executed.

This made it immediately usable as a drop-in replacement in existing models.

### Kernel fusion and tiling

The implementation fuses softmax, scaling, and matrix multiplication into a single kernel and processes attention in tiles that fit into on-chip memory. This minimizes costly reads and writes to high-bandwidth memory.

These low-level optimizations are central to the speedups achieved.

## Results

FlashAttention significantly reduces memory usage and improves training and inference speed, especially for long sequences. The gains grow with sequence length, making it particularly important for models with large context windows.

The paper demonstrates substantial speedups across a range of model sizes and hardware configurations.

## Impact

FlashAttention was rapidly adopted across major frameworks and model implementations. It became a standard component of training and inference stacks for large language models.

Subsequent versions extended the approach to support causal masking, dropout, and even longer contexts, further solidifying attention optimization as a systems problem.

## Modern perspective

Attention optimization is now treated as a core part of model design rather than an implementation detail. Many recent advances in long-context models build directly on the ideas introduced here.

FlashAttention also highlighted how hardware-aware algorithm design can yield gains comparable to architectural changes.

## Notes

This paper is best understood alongside code. The conceptual contribution is about data movement, not new modeling assumptions, and the practical impact comes from careful systems engineering.
