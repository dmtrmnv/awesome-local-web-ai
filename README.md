# Awesome Local Web AI
![Last Commit](https://img.shields.io/github/last-commit/dmtrmnv/awesome-local-web-ai)
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

> A curated list of frameworks, models, tools, and resources for running AI (LLMs, multimodal, audio, vision, agents) **locally in web browsers**.

🌐 **Focus:** Client-side inference, privacy-first AI, WebGPU/WASM acceleration, offline capabilities, open standards.

📖 **Note:** This list is community-maintained. Not affiliated with any specific organization.

## 📑 Table of Contents
- [🧠 Frameworks & Libraries](#-frameworks--libraries)
- [📦 Models & Weights](#-models--weights)
- [🎙️ Audio & Speech](#️-audio--speech)
- [🖼️ Image Generation & Vision](#️-image-generation--vision)
- [🔌 Browser-Native AI APIs](#-browser-native-ai-apis)
- [🔍 RAG & Vector Search](#-rag--vector-search)
- [🤖 Agents & Tool Use](#-agents--tool-use)
- [⚡ Standards & APIs](#-standards--apis)
- [🛠 Tools & Utilities](#-tools--utilities)
- [🌐 Demos & Examples](#-demos--examples)
- [🌐 Browser Compatibility](#-browser-compatibility)
- [📚 Learning & Tutorials](#-learning--tutorials)
- [🤝 Communities & News](#-communities--news)
- [📜 Contributing](#-contributing)
- [📝 License](#-license)

## 🧠 Frameworks & Libraries

### LLM Inference
- [WebLLM](https://github.com/mlc-ai/web-llm) – High-performance LLM inference in the browser via WebGPU & MLC compiler. OpenAI-compatible API, function calling support. [Published at WWW 2025](https://arxiv.org/html/2412.15803v2).
- [wllama](https://github.com/ngxson/wllama) – Run GGUF models directly in the browser with WASM + WebGPU. Simple API, streaming, chat templates. [Presented at FOSDEM 2025](https://archive.fosdem.org/2025/schedule/event/fosdem-2025-5154-wllama-bringing-llama-cpp-to-the-web).
- [Transformers.js](https://github.com/huggingface/transformers.js) – Hugging Face ecosystem for the browser. v4 features a new C++ WebGPU runtime, support for 8B+ parameter models, and works in browser, Node.js, Bun, and Deno.
- [ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/) – Cross-browser ML runtime with stable WebGPU execution provider and WASM acceleration.
- [Candle](https://github.com/huggingface/candle) – HuggingFace's minimalist ML framework in Rust, compiles to WASM for browser inference. Supports LLaMA, Whisper, BERT, and more. Alternative path to Transformers.js with different performance characteristics.
- [picoLLM](https://github.com/Picovoice/picollm) – Cross-browser WASM-based LLM inference engine. Uniquely works on **all major browsers** including Safari, Firefox, Edge, and Opera — not just Chromium.

### Google AI Edge
- [MediaPipe LLM Inference API](https://ai.google.dev/edge/mediapipe/solutions/genai/llm_inference/web_js) – Google's official on-device LLM inference SDK via MediaPipe, WebGPU-accelerated, with first-class support for Gemma models.
- [LiteRT.js](https://ai.google.dev/edge/litert/web) – Google's high-performance WebAI runtime (2025), the web successor to TFLite. Runs `.tflite` models in-browser with WebGPU acceleration.

### Computer Vision & General ML
- [TensorFlow.js](https://github.com/tensorflow/tfjs) – Google's WebGL/WebGPU-accelerated ML library for JavaScript. Supports both training and inference in browser. The most mature framework for computer vision, audio, and custom models.
- [Roboflow Inference.js](https://github.com/roboflow/inference) – Browser-based real-time computer vision inference SDK. Run YOLO, segmentation, and classification models directly in the browser. [Presented at Web AI Summit 2024](https://web.dev/blog/web-ai-summit-2024-recap).

### Research & Experimental
- [WeInfer](https://github.com/csAugust/WeInfer) – Research WebGPU optimization framework for LLM inference in browsers. Introduces uniform buffer optimization and WebGPU-specific improvements. [Published at WWW 2025](https://dl.acm.org/doi/10.1145/3696410.3714553).
- [jax-js](https://github.com/ekzhang/jax-js) – JAX-style ML framework for the browser running on WebGPU & WASM. Brings high-performance CPU and GPU kernels to JavaScript with JIT compilation.

### Privacy-First & Agents
- [Mozilla AI](https://github.com/mozilla-ai) – Privacy-focused browser AI framework. Includes `wasm-agents-blueprint` for local agent workflows.

## 📦 Models & Weights

### Model Collections
- [GGUF Models (Browser-Ready)](https://huggingface.co/models?library=gguf&sort=trending) – Quantized models optimized for `wllama` & `llama.cpp`. Look for `≤7B` & `Q4_K_M`.
- [ONNX Models for Web](https://huggingface.co/models?library=transformers.js) – Pre-converted weights for `transformers.js`. Filter by `onnx` & `text-generation`.
- [MLC-Compiled Models](https://huggingface.co/models?library=mlc-llm) – Optimized for `WebLLM`. High throughput on WebGPU.

### Recommended Starters
| Model | Size | Best For | Runtime |
|-------|------|----------|---------|
| [Gemma 3n E2B](https://ai.google.dev/gemma/docs/gemma-3n) | 2B | Multimodal understanding, on-device | MediaPipe |
| [Qwen3-0.6B](https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f) | 0.6B | Ultra-fast responses, embedding | WebLLM / Transformers.js |
| [Qwen3-1.7B](https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f) | 1.7B | General chat, thinking mode | WebLLM / Transformers.js |
| [Phi-4-mini](https://azure.microsoft.com/en-us/products/phi) | 3.8B | Reasoning, built into Edge | Edge Built-in AI |
| [SmolLM2-1.7B](https://huggingface.co/collections/HuggingFaceTB/smollm2-672388321e1fac1c1aeb267e) | 1.7B | Lightweight assistant | Transformers.js |
| [DeepSeek-R1-Distill-Qwen-1.5B](https://huggingface.co/unsloth/DeepSeek-R1-Distill-Qwen-1.5B) | 1.5B | Reasoning, chain-of-thought | Transformers.js / WebGPU |
| [LFM2.5-350M](https://www.liquid.ai/blog/introducing-lfm2-5-the-next-generation-of-on-device-ai) | 350M | Agentic loops, ultra-fast | WebGPU |

### Notable Multimodal & Specialized Models
- [Qwen3.5-VL](https://huggingface.co/spaces/webml-community/Qwen3.5-WebGPU) – Vision-language model running in browser via WebGPU + Transformers.js. Image understanding + text generation.
- [Janus-Pro-1B](https://huggingface.co/spaces/webml-community/janus-pro-webgpu) – DeepSeek's unified multimodal model. Understands images AND generates images from text. 1B variant runs in browser.
- [LFM2.5-1.6B-VL](https://huggingface.co/spaces/LiquidAI/LFM2.5-VL-1.6B-WebGPU) – Vision-language variant of Liquid AI's on-device model family.
- [LFM2.5-1.5B-Audio](https://docs.liquid.ai/examples/web/audio-webgpu-demo) – Audio-language model running in browser via WebGPU.
- [LFM2.5-1.2B-Thinking](https://huggingface.co/spaces/LiquidAI/LFM2.5-1.2B-Thinking-WebGPU) – Reasoning/thinking model, 200+ tok/s on M4 Max in browser.
- [Kokoro-82M](https://huggingface.co/spaces/webml-community/kokoro-webgpu) – Text-to-speech model (82M parameters), real-time synthesis in browser via WebGPU.

### Legacy Models (Still Useful)
- `Llama-3.2-3B`, `Qwen2.5-0.5B`, `Gemma-2-2B` – Proven performers with extensive community support.

## 🎙️ Audio & Speech

### Speech-to-Text (ASR)
- [Whisper Web](https://whisperweb.dev) – OpenAI's Whisper speech-to-text running entirely in browser. Real-time transcription, 100+ languages, fully offline.
- [Whisper WebGPU](https://huggingface.co/spaces/Xenova/realtime-whisper-webgpu) – Real-time Whisper with WebGPU acceleration for near-instant transcription.
- [WebGPU Studio](https://github.com/jakerains/webgpustudio) – Full studio interface for real-time speech-to-text powered by Whisper with WebGPU acceleration.

### Text-to-Speech (TTS)
- [Kokoro TTS WebGPU](https://huggingface.co/spaces/webml-community/kokoro-webgpu) – Kokoro (82M parameter) TTS model running locally in browser via WebGPU. ~1 second for 10 seconds of speech.
- [TTSLab](https://news.ycombinator.com/item?id=47123980) – Open-source tool running both TTS and STT models in browser via WebGPU and WASM. Integrated voice AI agent lab.

### Voice Assistants
- Combine Whisper WebGPU + LLM (via WebLLM/Transformers.js) + Kokoro TTS for a complete voice assistant pipeline running entirely client-side.

## 🖼️ Image Generation & Vision

### Image Generation
- [web-stable-diffusion](https://github.com/mlc-ai/web-stable-diffusion) – Stable Diffusion models running entirely in browser with WebGPU. Text-to-image with zero server support. From the same team as WebLLM. [Demo](https://websd.mlc.ai).
- [Janus-Pro-1B](https://huggingface.co/spaces/webml-community/janus-pro-webgpu) – DeepSeek's unified model that both understands and generates images. The first model combining vision and image generation in browser.
- [Z-Image Turbo](https://community.intel.com/t5/Blogs/Tech-Innovation/Artificial-Intelligence-AI/From-U-Net-to-DiT-Z-Image-Turbo-Runs-in-Your-Browser/post/1743862) – DiT-based image generation model optimized for browser on Intel AI PCs via WebGPU.
- [Removerized](https://github.com/yossTheDev/removerized) – is an open-source, local-first AI image toolkit that runs entirely in the browser using ONNX Runtime Web.

### Vision Understanding
- [Qwen3.5-VL WebGPU](https://huggingface.co/spaces/webml-community/Qwen3.5-WebGPU) – Multimodal vision-language model for image understanding in browser.
- [LFM2.5-VL-1.6B WebGPU](https://huggingface.co/spaces/LiquidAI/LFM2.5-VL-1.6B-WebGPU) – Vision-language model from Liquid AI running in browser.

### Computer Vision
- [Roboflow Inference.js](https://github.com/roboflow/inference) – Real-time object detection (YOLO), segmentation, and classification directly in the browser.
- [TensorFlow.js Models](https://github.com/tensorflow/tfjs-models) – Pre-built models for pose estimation, object detection, text detection, and more.

## 🔌 Browser-Native AI APIs

No model download, no framework — just call browser APIs. This is the zero-config path to browser AI.

### Chrome Built-in AI (Gemini Nano)
- [Prompt API](https://developer.chrome.com/docs/ai/prompt-api) – Send prompts to the built-in Gemini Nano model. `window.ai.createTextSession()`.
- [Summarizer API](https://developer.chrome.com/docs/ai/summarizer-api) – Summarize text with a single API call.
- [Writer API](https://developer.chrome.com/docs/ai/writer-api) – Generate text for writing tasks (emails, articles, etc.).
- [Rewriter API](https://developer.chrome.com/docs/ai/rewriter-api) – Rewrite existing text with different tone or style.
- [Language Detector API](https://developer.chrome.com/docs/ai/language-detection) – Detect the language of input text.
- [Translator API](https://developer.chrome.com/docs/ai/translator-api) – Translate text between languages locally.
- [Proofreader API](https://developer.chrome.com/docs/ai/proofreader) – Check and correct grammar/spelling locally.
- [Chrome Built-in AI Docs](https://developer.chrome.com/docs/ai/built-in) – Official documentation for all built-in AI APIs.

### Edge Built-in AI (Phi-4-mini)
- [Edge Prompt API](https://learn.microsoft.com/en-us/microsoft-edge/web-platform/prompt-api) – Compatible with Chrome's Prompt API but uses Microsoft's Phi-4-mini model.
- [Edge Writer & Rewriter APIs](https://blogs.windows.com/msedgedev/2025/05/19/introducing-the-prompt-and-writing-assistance-apis) – Writing assistance APIs using Phi-4-mini, compatible with Chrome's API surface.

### Built-in AI Resources
- [Chrome Built-in AI Challenge 2025](https://googlechromeai2025.devpost.com) – Hackathon for building apps with browser AI APIs. Contains many example projects.
- [Chrome Web AI Demos (Google I/O 2025)](https://chrome.dev/web-ai-demos/io2025.html) – Official demos for built-in AI APIs.

## 🔍 RAG & Vector Search

- [DuckDB WASM](https://duckdb.org/docs/current/clients/wasm/overview.html) – DuckDB compiled to WASM for in-browser SQL analytics. No server needed.
- [DuckDB VSS Extension](https://duckdb.org/2024/05/03/vector-similarity-search-vss.html) – Vector Similarity Search with HNSW indexing, running in-browser via DuckDB WASM. Combined with embedding models from Transformers.js, enables fully client-side RAG pipelines.
- [Transformers.js Embeddings](https://huggingface.co/docs/transformers.js) – Generate text embeddings client-side for vector search and semantic similarity.

## 🤖 Agents & Tool Use

- [WebLLM Function Calling](https://github.com/mlc-ai/web-llm) – WebLLM supports function calling / tool use for building agent-like applications with OpenAI-compatible API.
- [Mozilla wasm-agents Blueprint](https://github.com/mozilla-ai/wasm-agents-blueprint) – Local AI agents running entirely in-browser using WASM workflows.
- [WebMCP](https://developers.googleblog.com/developers-guide-to-ai-agent-protocols) – Browser-native protocol (W3C proposed standard) that lets websites expose structured, callable tools to AI agents. Ships in Chrome 146+ Canary.
- [llamafile](https://github.com/mozilla-ai/llamafile) – Distribute and run LLMs with a single executable file. Bundles model weights + inference engine + runtime. Companion tool for heavier models that don't fit in browser.

## ⚡ Standards & APIs

- [WebGPU](https://www.w3.org/TR/webgpu/) – Next-gen browser graphics/compute API. Required for fast LLM inference. Now supported in **all major browsers** (Chrome 113+, Firefox 141+, Safari 26+).
- [WebNN](https://webmachinelearning.github.io/webnn/) – W3C standard for native hardware acceleration in browsers.
- [WebAssembly (WASM)](https://webassembly.org/) – Near-native performance in the browser. Backbone of `llama.cpp` & `transformers.js`.
- [Cache API & IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/Cache) – Essential for persisting large model weights between sessions.
- [WebGPU Subgroups & Cooperative Matrix Multiply](https://developer.chrome.com/blog/io24-webassembly-webgpu-2) – Upcoming WebGPU features enabling SIMD-level parallelism and tensor-core matrix multiplication. Under investigation by GPU Web Working Group.
- [SharedArrayBuffer + Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/SharedArrayBuffer) – Enables true parallel processing for multi-threaded model inference, concurrent processing, and multi-worker data pipelines.

## 🛠 Tools & Utilities

- [Optimum CLI](https://huggingface.co/docs/optimum) – Convert Hugging Face models to ONNX/Web-ready formats.
- [MLC LLM Compiler](https://github.com/mlc-ai/mlc-llm) – Compile models to MLC format for `WebLLM`.
- [llama.cpp GGUF Tools](https://github.com/ggerganov/llama.cpp) – Quantize, split, and validate GGUF files.
- [LiteRT Converter](https://ai.google.dev/edge/litert) – Convert and optimize models for LiteRT.js browser deployment.

## 🌐 Demos & Examples

### Official Playgrounds
- [WebLLM Playground](https://huggingface.co/spaces/mlc-ai/webllm-playground) – Official interactive demo.
- [Transformers.js Examples](https://github.com/huggingface/transformers.js-examples) – Code snippets for chat, classification, embeddings & more.
- [wllama Quickstart](https://github.com/ngxson/wllama) – Quickstart projects and examples.
- [Mozilla wasm-agents Demo](https://github.com/mozilla-ai/wasm-agents-blueprint) – Local AI agents running in-browser.

### WebGPU Demo Collections
- [webml-community Spaces](https://huggingface.co/spaces/webml-community) – The most comprehensive collection of WebGPU AI demos: Llama 3.2, Qwen3, Janus-Pro, Kokoro TTS, DeepSeek-R1, and more.
- [Community WebGPU Spaces](https://huggingface.co/spaces?search=webgpu+llm) – User-submitted experiments on HuggingFace.
- [Chrome Web AI Demos (Google I/O 2025)](https://chrome.dev/web-ai-demos/io2025.html) – Official Google demos for built-in AI APIs.

### Standout Demos
- [DeepSeek-R1 WebGPU](https://roryp.github.io/deepseek-r1-webgpu) – Reasoning model running in browser with chain-of-thought.
- [Qwen3 WebGPU](https://huggingface.co/spaces/webml-community/qwen3-webgpu) – Qwen3 running at ~100 tok/s on M4 Pro Max.
- [LFM2.5 WebGPU Demos](https://huggingface.co/spaces/LiquidAI/LFM2.5-1.2B-Thinking-WebGPU) – Vision, audio, and thinking model variants in browser.
- [web-stable-diffusion Demo](https://websd.mlc.ai) – Image generation in browser via WebGPU.
- [Simon Willison's Llama 3.2 WebGPU](https://simonwillison.net/2025/Sep/8/webgpu-local-folder) – Clean, minimal example for loading and running a model locally without any server.

## 🌐 Browser Compatibility

WebGPU support status across major browsers:

| Browser | WebGPU Support | Notes |
|---------|---------------|-------|
| Chrome | 113+ | Full support, primary development target |
| Edge | 113+ | Full support, includes built-in Phi-4-mini AI |
| Firefox | 141+ | Full support since v141 |
| Safari | 26+ | Available in macOS Tahoe, iOS 26, visionOS 26 ([WWDC 2025](https://developer.apple.com/videos/play/wwdc2025/236)) |

**Framework compatibility notes:**
- WebLLM, Transformers.js, web-stable-diffusion — Chrome/Edge (WebGPU), limited Firefox support
- picoLLM — All major browsers including Safari & Firefox (WASM-based)
- Chrome Built-in AI — Chrome 127+ only
- Edge Built-in AI — Edge only

## 📚 Learning & Tutorials

### Documentation
- [Transformers.js Documentation](https://huggingface.co/docs/transformers.js) – Official docs including v4 migration guide.
- [WebLLM Docs & Guides](https://webllm.mlc.ai/) – Official WebLLM documentation.
- [WebNN Intro & Explainer](https://webmachinelearning.github.io/webnn-intro/) – W3C WebNN introduction.
- [Chrome Built-in AI Docs](https://developer.chrome.com/docs/ai/built-in) – Complete guide to browser AI APIs.

### Tutorials & Guides
- [SitePoint: Local-First AI with WebGPU](https://www.sitepoint.com/local-first-ai-webgpu-chrome-guide) – Comprehensive guide to getting started with browser AI.
- [SitePoint: WebGPU vs WASM with Transformers.js](https://www.sitepoint.com/webgpu-vs-webasm-transformers-js) – Performance comparison and architecture guide.
- [SitePoint: Browser-Based RAG with Private Docs](https://www.sitepoint.com/browser-based-rag-private-docs) – Build a client-side RAG pipeline.
- [AI Competence: AI in Browser with WebGPU](https://aicompetence.org/ai-in-browser-with-webgpu) – Comprehensive 2025 developer guide covering frameworks, benchmarks, and best practices.

### Talks & Conferences
- [Web AI Summit 2024](https://web.dev/blog/web-ai-summit-2024-recap) – Google's annual conference on client-side AI. [YouTube playlist](https://www.youtube.com/playlist?list=PLNYkxOF6rcIAEVKJ98bDkQRkwvO4grhnt).
- [Google I/O 2025 Web AI Sessions](https://io.google/2025/explore/technical-session-42) – Official sessions on WebGPU + Built-in AI APIs.
- [WWDC 2025: WebGPU on Apple Platforms](https://developer.apple.com/videos/play/wwdc2025/236) – Apple's official WebGPU introduction for Safari.
- [FOSDEM 2025: wllama Talk](https://archive.fosdem.org/2025/schedule/event/fosdem-2025-5154-wllama-bringing-llama-cpp-to-the-web) – Bringing llama.cpp to the web.

### Blogs
- [Mozilla AI Blog](https://blog.mozilla.ai/) – Privacy-first AI research and updates.
- [Simon Willison's Blog](https://simonwillison.net) – Frequent, high-quality coverage of browser AI developments.

## 🤝 Communities & News

- 📡 **Reddit:** `r/LocalLLaMA`, `r/MachineLearning`, `r/webdev`, `r/LLMDevs`
- 💬 **Discord:** Hugging Face, MLC AI, Local AI Community
- 📰 **Newsletters:** TLDR AI, The Batch (DeepLearning.AI), Hugging Face Weekly, [Web AI Monthly](https://www.linkedin.com/pulse/web-ai-monthly-30-25b-downloads-webmcp-share-gpus-llm-jason-mayes-dvnie) (Jason Mayes, Google)
- 🔍 **Aggregators:** [LLM Stats](https://llm-stats.com/), [Papers With Code](https://paperswithcode.com/)
- 🏆 **Challenges:** [Chrome Built-in AI Challenge 2025](https://googlechromeai2025.devpost.com) – Build apps with browser AI APIs.

## 📜 Contributing
Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a PR.  
We welcome: new tools, model collections, tutorials, demo spaces, and browser-compatibility notes.  
**Requirements:** Open-source or freely accessible, actively maintained, relevant to client-side web AI.

## 📝 License
[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)  
To the extent possible under law, the author(s) have dedicated all copyright and related and neighboring rights to this work to the Public Domain.
