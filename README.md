# AdeLLM

A cybersecurity-oriented language model project built in three parts.

## Subprojects

| Repo | Description | Status |
|------|-------------|--------|
| [AdeLLM-trained](https://github.com/AnotherMedo/AdeLLM-trained) | GPT-style LLM trained from scratch on cybersecurity data | ✅ Complete |
| [AdeLLM-tuned](https://github.com/AnotherMedo/AdeLLM-tuned) | Fine-tuned Mistral/Llama using LoRA on cybersecurity data | 🚧 In progress |
| [AdeLLM-web](https://github.com/AnotherMedo/AdeLLM-web) | Chat interface for interacting with both models | 🚧 Planned |

## AdeLLM-trained Results

| Version | Params | Val Loss | Train Time |
|---------|--------|----------|------------|
| v1 | 30M | 2.89 | 23 min |
| v2 | 150M | 2.05 | 1h49m |

### Sample Output (v2, 150M params)

**Prompt:** `"A buffer overflow vulnerability occurs when"`

**Output:**
> A buffer overflow vulnerability occurs when the program calls to return 
> addresses or data in ways to be injected into a function pointer. In a 
> large way, this can lead to arbitrary code execution if the function has 
> been tampered with...

Model correctly references: return addresses, arbitrary code execution, 
function pointers, stack, memory corruption, JIT, side-channel attacks.

## Architecture

- GPT-style decoder-only transformer
- Trained on: `AlicanKiraz0/Cybersecurity-Dataset-Fenrir-v2.0` (46M tokens)
- Tokenizer: tiktoken gpt2 (vocab size 50,257)
- Hardware: AMD Radeon RX 9070 (ROCm)
