# TikToken Documentation

> Source: https://github.com/openai/tiktoken
> Cached: 2026-02-13

## Fast BPE Tokeniser for OpenAI Models

tiktoken is a fast BPE tokeniser for use with OpenAI's models.

## Installation

```bash
pip install tiktoken
```

## Quick Usage

```python
import tiktoken

# Get a specific encoding
enc = tiktoken.get_encoding("o200k_base")
assert enc.decode(enc.encode("hello world")) == "hello world"

# Get the tokeniser corresponding to a specific model in the OpenAI API
enc = tiktoken.encoding_for_model("gpt-4o")
```

## Performance

tiktoken is between 3-6x faster than a comparable open source tokeniser.

## What is BPE?

Language models don't see text like you and I, instead they see a sequence of numbers (known as tokens). Byte pair encoding (BPE) is a way of converting text into tokens. It has a couple desirable properties:

1. It's reversible and lossless, so you can convert tokens back into the original text
2. It works on arbitrary text, even text that is not in the tokeniser's training data
3. It compresses the text: the token sequence is shorter than the bytes corresponding to the original text. On average, in practice, each token corresponds to about 4 bytes.
4. It attempts to let the model see common subwords. For instance, "ing" is a common subword in English, so BPE encodings will often split "encoding" into tokens like "encod" and "ing".

## Educational Submodule

```python
from tiktoken._educational import *

# Train a BPE tokeniser on a small amount of text
enc = train_simple_encoding()

# Visualise how the GPT-4 encoder encodes text
enc = SimpleBytePairEncoding.from_tiktoken("cl100k_base")
enc.encode("hello world aaaaaaaaaaaa")
```

## Common Encodings

- `o200k_base` - Used by GPT-4o models
- `cl100k_base` - Used by GPT-4, GPT-3.5-turbo, text-embedding-ada-002
- `p50k_base` - Used by Codex models, text-davinci-002, text-davinci-003
- `r50k_base` (or `gpt2`) - Used by GPT-3 models
