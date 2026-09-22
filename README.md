# Week 6.1: LangGraph

## Introduction
LangGraph is a library designed to create complex applications using large language models (LLMs). It enables developers to build systems where various AI components interact and maintain state.

## Slides

[Slides](https://docs.google.com/presentation/d/1QQC4T1q-JoYLlZc781xeUm411ZbJ0eBXY1xMvYH1SX4/edit?usp=sharing)

## Prerequisites
Before you begin, ensure you have met the following requirements:
- Docker Desktop (recommended for local setup)
- Python 3.11.0 or greater (local setup with virtual environment)
- You'll need a free Tavily API key if you don't have one: [Tavily](https://tavily.com/)

### Set up environment variables:
- Copy the sample environment file:
  ```bash
  cp .env.sample .env
  ```
- Edit the `.env` file:
  ```
   OPENAI_API_KEY=your-openai-key
   LANGCHAIN_API_KEY=your-langchain-key
   LANGCHAIN_TRACING_V2=true
   LANGCHAIN_PROJECT=week_6_1
   TAVILY_API_KEY=your-tavily-key
  ```

The `LANGCHAIN_API_KEY` is obtained from **LangSmith**, LangChain’s tracing and observability platform. If you are looking for where to create this key, search for LangSmith rather than LangChain.
## Docker (recommended)
1. Run the first example (`simple_message_graph.py`):
   ```
   docker compose run --rm main python simple_message_graph.py
   ```
2. Start Jupyter to run the `.ipynb` files with a local notebook:
   ```
   docker compose up jupyter
   ```
3. Run any `.py` file in the root directory in this manner (ones you may create):
   ```
   docker compose run --rm main python <the_py_files>
   ```

## Running Different Scripts
You can use the provided `run.sh` script for easier execution.
Make sure to make the script executable with `chmod +x run.sh` in the CLI before using:
```bash
./run.sh main #(runs the simple_message_graph.py file)
./run.sh jupyter #(starts the jupyter notebook server)
./run.sh <your_new_py_file> #(runs other .py file)
```
## Local Setup (Alternative to Docker)
If you prefer to run the examples locally:

1. Ensure you have Python 3.11.0 or higher installed.
2. Clone the repository:
    ```bash
    git clone [repository-url]
    cd [repository-name]
    ```
3. Set up the virtual environment:
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
    pip install -r requirements.txt
    ```
4. Configure environment variables as described in the Setup section.
5. Export your `.env` variables to the system (python-dotenv should handle this for you in the main `simple_message_graph.py` and `multi-agent-collaboration.ipynb` files, but this is included for reference):
   **Linux / Mac / Bash**
      ```bash
      export $(grep -v '^#' .env | xargs)
      ```
5. Run the notebook:
    ```
    run the .ipynb file in VSCode (it will prompt you to allow the installation of ipykernel: do so) or in another IDE that supports Jupyter notebooks
    ```
## Need Help?
Reach out to the learning assistants
