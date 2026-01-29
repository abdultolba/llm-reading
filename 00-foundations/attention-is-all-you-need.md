# Attention Is All You Need (2017)

**Authors:** Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit,  
Llion Jones, Aidan N. Gomez, Łukasz Kaiser, Illia Polosukhin  
**Link:** https://arxiv.org/abs/1706.03762

## Why this paper matters

This paper introduced the **Transformer**, a neural network architecture that replaced recurrence and convolution with attention mechanisms alone. It became the foundation for virtually all modern large language models.

The key insight was that _self-attention_ can capture relationships among all positions in a sequence efficiently, and the entire model can be trained in parallel. This innovation made training on large datasets feasible and scalable.

## Core ideas

### Self-attention and multi-head attention

The Transformer uses **scaled dot-product attention** to compute dependencies between every pair of positions in the input. Rather than processing sequences one step at a time, every token attends to every other token at once. Multi-head attention runs several attention computations in parallel with different learned projections.

### Encoder–decoder structure

The model retains an encoder-decoder design:

- The **encoder** is a stack of identical layers that use self-attention then position-wise feed-forward networks.
- The **decoder** similarly uses self-attention, but also attends to the encoder’s output while generating each token.

### Positional encoding

Self-attention has no inherent notion of order. The authors add **positional encodings** to input embeddings to give the model a sense of token order.

## Results

On machine translation benchmarks, the Transformer matched or exceeded the state of the art at the time while training faster and more efficiently:

- English–German translation quality improved versus previous models.
- English–French translation achieved strong BLEU scores with reduced training time.

## Impact

Almost every major language model since has been built on Transformer variants. Architectures like BERT, GPT, and T5 all trace back to ideas in this paper. Its emphasis on attention and parallel training reshaped deep learning research and engineering.

## Notes

- This work reduced dependence on recurrent or convolutional structures and made large-scale training practical.
- The combination of self-attention and position-wise feed-forward layers became the standard building block for modern LLMs.
