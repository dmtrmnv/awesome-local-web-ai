# Awesome Local Web AI
![Last Commit](https://img.shields.io/github/last-commit/dmtrmnv/awesome-local-web-ai)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

> A curated list of frameworks, models, tools, and resources for running AI (LLMs, multimodal, audio, vision) **locally in web browsers**.

🌐 **Focus:** Client-side inference, privacy-first AI, WebGPU/WASM acceleration, offline capabilities, open standards.

📖 **Note:** This list is community-maintained. Not affiliated with any specific organization.

## 📑 Table of Contents
- [🧠 Frameworks & Libraries](#-frameworks--libraries)
- [📦 Models & Weights](#-models--weights)
- [⚡ Standards & APIs](#-standards--apis)
- [🛠 Tools & Utilities](#-tools--utilities)
- [🌐 Demos & Examples](#-demos--examples)
- [📚 Learning & Tutorials](#-learning--tutorials)
- [🤝 Communities & News](#-communities--news)
- [📜 Contributing](#-contributing)
- [📝 License](#-license)

## 🧠 Frameworks & Libraries
- [WebLLM](https://github.com/mlc-ai/web-llm) – High-performance LLM inference in the browser via WebGPU & MLC compiler.
- [wllama](https://github.com/ngxson/wllama) – Run GGUF models directly in the browser with WASM + WebGPU. Simple API, streaming, chat templates.
- [Transformers.js](https://github.com/huggingface/transformers.js) – Hugging Face ecosystem for the browser. Supports LLMs, vision, audio & embeddings (ONNX/WASM/WebGPU).
- [Mozilla AI](https://github.com/mozilla-ai) – Privacy-focused browser AI framework. Includes `wasm-agents-blueprint` for local agent workflows.
- [MediaPipe LLM Inference](https://ai.google.dev/edge/mediapipe/solutions/genai/llm_inference/web) – Google's optimized solution for mobile & desktop browsers.
- [ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/) – Cross-browser ML runtime with WebGPU/WASM acceleration.
- [llama.cpp (WASM/WebGPU port)](https://github.com/ggerganov/llama.cpp/tree/master/emscripten) – Reference C++ implementation compiled to WebAssembly. DIY-friendly.

## 📦 Models & Weights
- [GGUF Models (Browser-Ready)](https://huggingface.co/models?library=gguf&sort=trending) – Quantized models optimized for `wllama` & `llama.cpp`. Look for `≤7B` & `Q4_K_M`.
- [ONNX Models for Web](https://huggingface.co/models?library=transformers.js) – Pre-converted weights for `transformers.js`. Filter by `onnx` & `text-generation`.
- [MLC-Compiled Models](https://huggingface.co/models?library=mlc-llm) – Optimized for `WebLLM`. High throughput on WebGPU.
- **Recommended Starters:** `Llama-3.2-3B`, `Phi-3-mini`, `Qwen2.5-0.5B`, `Gemma-2-2B`, `SmolLM2-1.7B`.

## ⚡ Standards & APIs
- [WebGPU](https://www.w3.org/TR/webgpu/) – Next-gen browser graphics/compute API. Required for fast LLM inference.
- [WebNN](https://webmachinelearning.github.io/webnn/) – W3C standard for native hardware acceleration in browsers.
- [WebAssembly (WASM)](https://webassembly.org/) – Near-native performance in the browser. Backbone of `llama.cpp` & `transformers.js`.
- [Cache API & IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/Cache) – Essential for persisting large model weights between sessions.

## 🛠 Tools & Utilities
- [Optimum CLI](https://huggingface.co/docs/optimum) – Convert Hugging Face models to ONNX/Web-ready formats.
- [MLC LLM Compiler](https://github.com/mlc-ai/mlc-llm) – Compile models to MLC format for `WebLLM`.
- [llama.cpp GGUF Tools](https://github.com/ggerganov/llama.cpp) – Quantize, split, and validate GGUF files.
- [WebGPU Inspector](https://github.com/google/webgpu-inspector) – Debug WebGPU support & performance in browsers.
- [Browser AI Benchmark Suite](https://github.com/webml-community/webgpu-llm-benchmark) – Measure tok/s, memory & latency across frameworks.

## 🌐 Demos & Examples
- [WebLLM Playground](https://huggingface.co/spaces/mlc-ai/webllm-playground) – Official interactive demo.
- [Transformers.js Examples](https://huggingface.co/docs/transformers.js/examples) – Code snippets for chat, classification, embeddings & more.
- [wllama React/Vite Template](https://github.com/ngxson/wllama/tree/main/examples) – Quickstart projects.
- [Mozilla wasm-agents Demo](https://github.com/mozilla-ai/wasm-agents-blueprint) – Local AI agents running in-browser.
- [Community WebGPU Spaces](https://huggingface.co/spaces?search=webgpu+llm) – User-submitted experiments.

## 📚 Learning & Tutorials
- [Transformers.js Documentation](https://huggingface.co/docs/transformers.js)
- [WebLLM Docs & Guides](https://webllm.mlc.ai/)
- [WebGPU for Machine Learning](https://developer.chrome.com/blog/webgpu-ml/)
- [Running GGUF in the Browser (wllama)](https://github.com/ngxson/wllama#readme)
- [Mozilla AI Blog](https://blog.mozilla.ai/)
- [WebNN Intro & Explainer](https://webmachinelearning.github.io/webnn-intro/)

## 🤝 Communities & News
- 🐦 **Twitter/X:** `@mlc_ai`, `@huggingface`, `@ggerganov`, `@ngxson`, `@mozilla`
- 📡 **Reddit:** `r/LocalLLaMA`, `r/MachineLearning`, `r/webdev`
- 💬 **Discord:** Hugging Face, MLC AI, Local AI Community
- 📰 **Newsletters:** TLDR AI, The Batch (DeepLearning.AI), Hugging Face Weekly
- 🔍 **Aggregators:** [LLM Stats](https://llm-stats.com/), [Papers With Code](https://paperswithcode.com/)

## 📜 Contributing
Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a PR.  
We welcome: new tools, model collections, tutorials, demo spaces, and browser-compatibility notes.  
**Requirements:** Open-source or freely accessible, actively maintained, relevant to client-side web AI.

## 📝 License
[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)  
To the extent possible under law, the author(s) have dedicated all copyright and related and neighboring rights to this work to the Public Domain.
