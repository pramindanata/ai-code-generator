# AI Code Generator

An AI-powered **web application generator** built with **Gradio** and **DeepSeek API** (via the OpenAI-compatible client). Describe any web app you want, and the AI generates the full project — HTML, CSS, JavaScript, and more — writing files directly into a unique project folder.

## Prerequisites

- [pyenv](https://github.com/pyenv/pyenv) — Python version management
- [uv](https://docs.astral.sh/uv/) — Python package & project manager

## Todo

- [ ] Stream the AI's responses when creating the web project in real-time instead of waiting for the full response. User need to know the progress of the project creation.
- [ ] Create new project IDs in a session. Current implementation only create and use a single project ID in a session, which is not ideal for multiple requests.

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

## How It Works

1. Each chat session gets a **unique project ID** (e.g. `projects/5irzdxgs/`).
2. The AI is instructed to act as a web app builder — you describe what you want, and it chooses the best tech stack.
3. The AI responds with **tool calls** that write files (`.html`, `.css`, `.js`, etc.) into the project folder.
4. If the AI needs to write multiple files (e.g. a full Todo app with separate HTML/CSS/JS), it creates them in a single turn via **function calling**.
5. Open the generated `index.html` in your browser to see the result.

## Usage

Describe any web application you'd like the AI to build. Here are some example prompts:

- *"Create a todo list app with a clean UI"*
- *"Build a shopping cart page for an e-commerce store"*
- *"Make a personal portfolio/profile page"*
- *"Create a weather dashboard with a search bar"*
- *"Build a calculator app"*

## Generated Projects

Every session creates a subdirectory under `projects/` with a random 8-character ID. Each project contains the files the AI wrote for that request.
