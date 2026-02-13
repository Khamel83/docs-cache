# Transformers Documentation

> Source: https://huggingface.co/docs/transformers/index
> Cached: 2026-02-13

## State-of-the-Art Machine Learning

Transformers acts as the model-definition framework for state-of-the-art machine learning models in text, computer vision, audio, video, and multimodal models, for both inference and training.

It centralizes the model definition so that this definition is agreed upon across the ecosystem. `transformers` is the pivot across frameworks: if a model definition is supported, it will be compatible with the majority of training frameworks (Axolotl, Unsloth, DeepSpeed, FSDP, PyTorch-Lightning), inference engines (vLLM, SGLang, TGI), and adjacent modeling libraries (llama.cpp, mlx).

There are over **1M+ Transformers model checkpoints** on the Hugging Face Hub you can use.

## Features

Transformers provides everything you need for inference or training with state-of-the-art pretrained models:

- **Pipeline**: Simple and optimized inference class for many machine learning tasks like text generation, image segmentation, automatic speech recognition, document question answering, and more.
- **Trainer**: A comprehensive trainer that supports features such as mixed precision, torch.compile, and FlashAttention for training and distributed training for PyTorch models.
- **generate**: Fast text generation with large language models (LLMs) and vision language models (VLMs), including support for streaming and multiple decoding strategies.

## Design Principles

Transformers is designed for developers and machine learning engineers and researchers:

1. **Fast and easy to use**: Every model is implemented from only three main classes (configuration, model, and preprocessor) and can be quickly used for inference or training with Pipeline or Trainer.
2. **Pretrained models**: Reduce your carbon footprint, compute cost and time by using a pretrained model instead of training an entirely new one. Each pretrained model is reproduced as closely as possible to the original model and offers state-of-the-art performance.

## Quick Example

```python
from transformers import pipeline

# Text generation
generator = pipeline('text-generation', model='gpt2')
result = generator("Hello, I'm a language model,", max_length=30)

# Sentiment analysis
classifier = pipeline('sentiment-analysis')
result = classifier("I love using Transformers!")
```

## Learning Resources

If you're new to Transformers or want to learn more about transformer models, check out the Hugging Face LLM course. This comprehensive course covers everything from the fundamentals of how transformer models work to practical applications across various tasks.
