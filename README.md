# MiniGPT 🚀

A GPT-style language model built completely from scratch in **PyTorch** for educational purposes.

This project implements the complete GPT pipeline, including tokenizer training, Transformer architecture, language model training, and text generation without relying on pre-built GPT implementations.

---

# Features

- ✅ Custom BPE Tokenizer
- ✅ Token Embeddings
- ✅ Positional Embeddings
- ✅ Multi-Head Self-Attention
- ✅ Feed Forward Network (FFN)
- ✅ Residual Connections
- ✅ Layer Normalization
- ✅ Transformer Decoder Blocks
- ✅ Weight Tying (GPT-2 Style)
- ✅ Cross Entropy Loss
- ✅ AdamW Optimizer
- ✅ Temperature Sampling
- ✅ Top-k Sampling
- ✅ Top-p (Nucleus) Sampling
- ✅ EOS Stopping
- ✅ Model Checkpoint Saving & Loading

---

# Model Architecture

| Parameter | Value |
|-----------|------:|
| Model Type | Decoder-only Transformer |
| Layers | 4 |
| Attention Heads | 4 |
| Embedding Dimension | 256 |
| Feed Forward Dimension | 1024 |
| Context Length | 128 |
| Vocabulary Size | 8000 |
| Total Parameters | ~5.2 Million |

---

# Dataset

The model is trained on:

- **TinyStories**
- Approximately **1,000 stories** (initial experiment)

Dataset:

https://huggingface.co/datasets/roneneldan/TinyStories

---

# Tokenizer

A Byte Pair Encoding (BPE) tokenizer was trained from scratch using the TinyStories dataset.

Special tokens:

- `<pad>`
- `<bos>`
- `<eos>`
- `<unk>`

Vocabulary Size:

```
8000
```

---

# Training

Optimizer

```
AdamW
```

Loss Function

```
CrossEntropyLoss
```

Learning Rate

```
3e-4
```

Batch Size

```
16
```

Epochs

```
20
```

---

# Text Generation

MiniGPT supports multiple decoding strategies:

- Greedy Decoding
- Temperature Sampling
- Top-k Sampling
- Top-p (Nucleus) Sampling

Example:

```python
output = model.generate(
    input_ids,
    max_new_tokens=200,
    temperature=0.8,
    top_k=100,
    top_p=0.9,
)
```

---

# Example Output

### Prompt

```
Once upon a time
```

### Output

```
There was a little girl with dark hair and a smile.
She was very happy.
She ran to her mom and showed her the new dress.
Her mom smiled and said,
"Thank you, Lily.
You are a very good girl."

Lily smiled and said,
"I love you too, mom.
You are very kind."
```

---

# Project Structure

```
MiniGPT
│
├── src/
│   ├── attention.py
│   ├── config.py
│   ├── dataset.py
│   ├── embeddings.py
│   ├── feedforward.py
│   ├── model.py
│   ├── trainer.py
│   └── transformer.py
│
├── tokenizer/
│   ├── tokenizer.json
│   └── tokenizer_config.json
│
├── train.py
├── generate.py
├── train_tokenizer.py
└── README.md
```

---

# Future Improvements

- Larger model architecture
- More training data
- Validation dataset
- Learning rate scheduler
- Mixed precision (AMP)
- Flash Attention
- KV Cache for faster inference
- Hugging Face Transformers compatibility
- Model quantization
- Fine-tuning support

---

# Purpose

This project was created to understand how GPT-style language models work internally by implementing every major component from scratch instead of using existing GPT implementations.

The goal is educational: to learn the architecture, training process, and text generation pipeline of modern decoder-only Transformer language models.

---

# Tech Stack

- Python
- PyTorch
- Hugging Face Datasets
- Hugging Face Tokenizers
- Transformers

---

# License

MIT License

---

⭐ If you found this project interesting or helpful, consider giving it a star!
