# AlphaZip

Welcome to the **AlphaZip - Neural Networks Enhanced Lossless Text Compression** project! This project explores leveraging the power of Large Language Models (LLMs) for compressing text in a lossless manner using rank-based prediction followed by compression techniques.

Find the pre-print here: https://arxiv.org/abs/2409.15046

## Overview

Our approach utilizes advanced neural network models to achieve efficient and effective text compression. For  real-time text file compression on your personal computer refer to the instructions below.

## Requirements

To get started, ensure you have the following:

- **NVIDIA GPU**: GeForce RTX 4080
- **Python**: 3.10.12
- **PyTorch**: 2.2.2
- **TensorFlow**: 2.11.0 (for XLA support)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/Swathi-Shree-Narashiman/AlphaZip.git
    ```

2. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Compressing Text Files**:
    - Use the `compress.py` script to compress any text file.
    - Modify the `path` variable in the script to point to your file.

2. **PDF Files**:
    - Utilize the `read_PDF` function to extract text from a PDF.
    - Save the extracted text to a file and then compress it using the `compress.py` script.

3. **Adaptive Huffman Method**:
    - To use the adaptive Huffman method, either copy and paste the function or import it as a user-defined library.

## Hyperparameters

- **`input_length`**: Number of ASCII characters from the input text to compress.
- **`context_size`**: Number of characters used as context for the transformer block to predict the next token.

## Domain-Specific Compression

### Fine-Tuning

To fine-tune the model:

Create a directory inside your current directory using
```bash
    mkdir fine_tuning_weights
```

1. Run the `PEFT/fine_tuning.py` script with your input file, e.g., `input.txt`.

    ```bash
    python PEFT/fine_tuning.py <input.txt>
    ```

2. Test compression performance from any checkpoint using `compress.py`:

    ```bash
    python compress.py <file_to_be_compressed_path> <current_directory_path/fine_tuning_weights/checkpoint-XXXX>
    ```
   Replace XXXX with the checkpoint you would like to load.

### Knowledge Distillation

To perform knowledge distillation on GPT-2:

Create a directory inside your current directory using
```bash
    mkdir knowledge_distillation_weights
```

1. Run the `PEFT/knowledge_distillation.py` script with your input file, e.g., `input.txt`.

    ```bash
    python PEFT/knowledge_distillation.py <input.txt>
    ```

2. Test compression performance from any checkpoint using `compress.py`:

    ```bash
    python compress.py <file_to_be_compressed_path> <current_directory_path/knowledge_distillation_weights/checkpoint-XXXX>
    ```
Replace XXXX with the checkpoint you would like to load.



---

Feel free to modify any paths or links to fit your specific repository details. This `README.md` file provides a clear and organized overview of your project, making it easier for users to get started and understand how to use the code.

