<div align="center">
  <img src="media/Horus%20Hiero.png" alt="Horus-Hiero" width="600"/>
  <h1>Horus-Hiero</h1>
  <p><b>Understanding the Language of the Pharaohs</b></p>
</div>

<p align="center">
  <a href="https://huggingface.co/collections/tokenaii/horus-hiero"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Collection-yellow" /></a>
  <a href="https://huggingface.co/tokenaii"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Organization-blue" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache%202.0-green" /></a>
</p>

**Horus-Hiero** is a specialized AI model dedicated to translating ancient Egyptian hieroglyphs into modern languages. Developed by TokenAI, it bridges the gap between the language of the Pharaohs and today's world.

---

## Models

| Model | Size | Format | Description |
|-------|------|--------|-------------|
| [Horus-Hiero-9B](https://huggingface.co/tokenaii/Horus-Hiero-9B) | 9B params | Full weights (safetensors) | Full-precision 16-bit model for maximum quality |
| [Horus-Hiero-9B-GGUF](https://huggingface.co/tokenaii/Horus-Hiero-9B-GGUF) | 9B params | GGUF (Q2\_K to Q8\_0) | Quantized versions for efficient deployment |
| [Horus-Hiero-Mini-4B](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B) | 4B params | Full weights (safetensors) | Compact model for resource-constrained setups |
| [Horus-Hiero-Mini-4B-GGUF](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B-GGUF) | 4B params | GGUF (Q2\_K to Q8\_0) | Quantized versions of the Mini model |

### GGUF Quantization Variants

**Horus-Hiero-9B-GGUF:**

| Quant | Size | Download |
|-------|------|----------|
| Q8\_0 | ~8.9 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-9B-GGUF/resolve/main/Horus-Hiero-9B-Q8_0.gguf) |
| Q6\_K | ~6.9 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-9B-GGUF/resolve/main/Horus-Hiero-9B-Q6_K.gguf) |
| Q4\_K\_M | ~5.2 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-9B-GGUF/resolve/main/Horus-Hiero-9B-Q4_K_M.gguf) |
| Q2\_K | ~3.6 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-9B-GGUF/resolve/main/Horus-Hiero-9B-Q2_K.gguf) |

**Horus-Hiero-Mini-4B-GGUF:**

| Quant | Size | Download |
|-------|------|----------|
| Q8\_0 | ~4.2 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B-GGUF/resolve/main/Horus-Hiero-Mini-4B-Q8_0.gguf) |
| Q6\_K | ~3.2 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B-GGUF/resolve/main/Horus-Hiero-Mini-4B-Q6_K.gguf) |
| Q4\_K\_M | ~2.5 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B-GGUF/resolve/main/Horus-Hiero-Mini-4B-Q4_K_M.gguf) |
| Q2\_K | ~1.8 GB | [Download](https://huggingface.co/tokenaii/Horus-Hiero-Mini-4B-GGUF/resolve/main/Horus-Hiero-Mini-4B-Q2_K.gguf) |

---

## Usage

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model = AutoModelForCausalLM.from_pretrained("tokenaii/Horus-Hiero-9B", torch_dtype="auto")
tokenizer = AutoTokenizer.from_pretrained("tokenaii/Horus-Hiero-9B")

prompt = "Translate this hieroglyph: ..."
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(**inputs)
print(tokenizer.decode(outputs[0]))
```

**With llama.cpp (GGUF):**

```bash
./llama-cli -m Horus-Hiero-9B-Q4_K_M.gguf -p "Your prompt" -ngl 99
```

---

## Links

- [Hugging Face Collection](https://huggingface.co/collections/tokenaii/horus-hiero)
- [TokenAI Organization](https://huggingface.co/tokenaii)
- [TokenAI Website](https://tokenai.cloud)
- [GitHub](https://github.com/tokenaii)

---

## License

This project is licensed under the [Apache License 2.0](LICENSE).
