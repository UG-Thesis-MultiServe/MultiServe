# MultiServe


## 🚀 MultiServe: Efficient Tool-Augmented Inference with Collaborative LLMs

![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)
![GPU](https://img.shields.io/badge/GPU-NVIDIA%20H100-green)
![LLM](https://img.shields.io/badge/Model-LLaMA3%2070B-purple)

> A collaborative LLM inference framework that combines speculative inference, dynamic cache scheduling, and tool augmentation – for blazing-fast, memory-efficient, and secure multi-agent reasoning 🔧🧠⚡️
>
> *Refining is in progress and will be open source soon.*

---

## ✨ Features

- 🤖 **Dual-Model Collaboration**  
  Leverage a lightweight **Speculative Model** to predict tool calls and prefetch responses, while a heavyweight **Decode Model** generates high-fidelity outputs.

- 📦 **Fine-Grained KV Cache Management**  
  Smart cache partitioning, swapping, and prefix reuse using block-based scheduling and Radix Attention-inspired hashing.

- 🔁 **Tool-Augmented Speculative Decoding**  
  Seamlessly integrate external tools (e.g., calculators, search engines) into the reasoning pipeline with asynchronous orchestration.

- 🛡️ **Resource-Aware Scheduling**  
  Dynamically reallocate GPU memory based on queue pressure and model load, improving throughput and robustness under heavy concurrency.

- 📈 **SOTA Performance**  
  Achieves **2×–3× speedups** over existing LLM serving frameworks like vLLM and InferCept on benchmarks like GSM8K and HotpotQA.

---

## 📊 Benchmark Results

| Task     | Latency ↓ | Throughput ↑ | Accuracy |
| -------- | --------- | ------------ | -------- |
| GSM8K    | 2.7×      | +180%        | ✅        |
| HotpotQA | 1.3×      | +95%         | ✅        |

---

## 🔧 Getting Started

```bash
# Clone the repo
git clone https://github.com/UG-Thesis-MultiServe/MultiServe.git
cd MultiServe

# Install dependencies
conda env create -f environment.yml
conda activate multiserve

# Run server
python launch.py --config configs/llama3-70b.yaml
```

> 📌 Note: Tested on 4× NVIDIA H100 GPUs with PyTorch 2.1, CUDA 12.2, and vLLM backend.

---

## 📜 License

This project is licensed under the **Apache License 2.0**.
Feel free to use, modify, and redistribute with proper attribution. ❤️

---

## 🙌 Acknowledgements

Built on top of ideas from [vLLM](https://github.com/vllm-project/vllm), [FlexGen](https://github.com/FMInference/FlexGen), and inspired by ReAct and speculative decoding research.
Special thanks to the faculty and research mentors at **USTC** and **UC San Diego**. 🎓🇨🇳
