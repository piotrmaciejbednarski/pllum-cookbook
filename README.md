# PLLuM-8x7B-chat-GGUF Examples

This repository contains example Jupyter notebooks demonstrating how to use the quantized versions of the [PLLuM-8x7B-chat](https://huggingface.co/CYFRAGOVPL/PLLuM-8x7B-chat) model in GGUF format.

<p align="center">
  <img src="https://pllum.org.pl/_nuxt/PLLuM_logo_RGB_color.DXNEc-VR.png" width="400">
</p>

## Overview

PLLuM (Polish Large Language Model) is an advanced family of Polish language models developed by the Polish Ministry of Digital Affairs. The quantized versions in GGUF format allow for efficient running on consumer hardware with reduced memory requirements while maintaining good quality of generated text.

This repository provides practical examples of how to use these models with different libraries and approaches.

## Requirements

To run the examples, you'll need:

```bash
pip install -r requirements.txt
```

The requirements.txt file includes:
- jupyter
- llama-cpp-python
- transformers
- accelerate
- sentencepiece
- matplotlib
- pandas
- gradio (optional, for web UI examples)

## Available Examples

The repository contains the following example notebooks:

1. [`basic_inference.ipynb`](notebooks/basic_inference.ipynb) - Basic text generation using llama-cpp-python
2. [`chat_completion.ipynb`](notebooks/chat_completion.ipynb) - Chat completion interface with conversation history
3. [`model_comparison.ipynb`](notebooks/model_comparison.ipynb) - Comparison between different quantization levels
4. [`gradio_web_ui.ipynb`](notebooks/gradio_web_ui.ipynb) - Simple web interface using Gradio

## Model Variants

The examples work with all available quantized versions:

| Quantization | Size | Recommended for |
|--------------|------|-----------------|
| Q2_K | 17 GB | Minimal resources, lower quality |
| IQ3_S | 20.4 GB | Low resources with acceptable quality |
| Q3_K_M | 22.5 GB | Good balance for CPU usage |
| Q4_K_M | 28.4 GB | Recommended for most applications |
| Q5_K_M | 33.2 GB | High quality with reasonable size |
| Q8_0 | 49.6 GB | Highest quantized quality |
| F16/BF16 | ~85 GB | Reference without quantization |

## How to Download Models

You can download the models from [Hugging Face](https://huggingface.co/piotrmaciejbednarski/PLLuM-8x7B-chat-GGUF) using:

```bash
# Install huggingface-cli
pip install -U "huggingface_hub[cli]"

# Download a specific model (e.g., q4_k_m)
huggingface-cli download piotrmaciejbednarski/PLLuM-8x7B-chat-GGUF --include "PLLuM-8x7B-chat-gguf-q4_k_m.gguf" --local-dir ./models/

# For faster downloads
pip install hf_transfer
HF_HUB_ENABLE_HF_TRANSFER=1 huggingface-cli download piotrmaciejbednarski/PLLuM-8x7B-chat-GGUF --include "PLLuM-8x7B-chat-gguf-q4_k_m.gguf" --local-dir ./models/
```

## Getting Started

1. Clone this repository:
```bash
git clone https://github.com/piotrmaciejbednarski/pllum-examples.git
cd pllum-examples
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download a model using the instructions above

4. Start Jupyter:
```bash
jupyter notebook
```

5. Open one of the example notebooks in the `notebooks/` directory

## License

This repository is provided under the [Apache License 2.0](LICENSE), the same license as the original PLLuM model.

## Credits

- Original PLLuM model developed by [CYFRAGOVPL](https://huggingface.co/CYFRAGOVPL)
- GGUF quantization by [Piotr Bednarski](https://github.com/piotrmaciejbednarski)
- Examples in this repository by [Piotr Bednarski](https://github.com/piotrmaciejbednarski)