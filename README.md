# AI Code Generator

A simple AI-powered code generator built with **Gradio** and **DeepSeek API** (via the OpenAI-compatible client).

## Prerequisites

- [pyenv](https://github.com/pyenv/pyenv) — Python version management
- [uv](https://docs.astral.sh/uv/) — Python package & project manager

## Setup

1. **Clone the repository** and navigate into the project directory:

   ```bash
   cd ai-code-generator
   ```

2. **Set up environment variables:**

   ```bash
   cp .env.example .env
   ```

   Then edit `.env` and replace `your-api-key-here` with your actual DeepSeek API key.

3. **Install dependencies:**

   ```bash
   uv sync
   ```

   This creates a virtual environment (`.venv/`) and installs all required packages.

## Running the App

Open `notebook.ipynb` in VS Code, select the `.venv` kernel (Python 3.12), then run all cells. The Gradio interface will launch in your browser.

Alternatively, you can run the notebook from the terminal:

```bash
uv run jupyter notebook notebook.ipynb
```

## Usage

1. Launch the app (the Gradio UI opens in your browser).
2. Type a code request in the chat box (e.g., "Write a Python function to sort a list").
3. The AI will generate and stream the code response.
