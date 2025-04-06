# Wikipedia Summarizer MCP Server

A Model Client Protocol (MCP) server that fetches Wikipedia articles and summarizes them using Ollama LLM models.

## Overview

This project consists of three main components:
- **Ollama Server**: An MCP server that provides a tool to summarize Wikipedia articles using Ollama LLM models
- **Command-line Client**: A client that can connect to the MCP server and request article summaries
- **Streamlit Interface**: A web UI that provides a user-friendly way to interact with the MCP server

## Prerequisites

- Python 3.8+
- Ollama installed and running locally with the `deepseek-r1:1.5b` model (or update the model in `ollama_server.py`)
- Internet connection to fetch Wikipedia articles

## Installation

1. Clone this repository
2. Install the required packages:
   ```bash
   uv pip install -r requirements.txt
   ```

## Running the Server

Start the MCP server:
```bash
uv run -- ollama_server.py
```

The server will be available at `http://localhost:8000/sse`.

## Using the Command-line Client

```bash
uv run -- updated_client.py http://localhost:8000/sse https://en.wikipedia.org/wiki/Python_(programming_language)
```

## Using the Streamlit Interface

Start the Streamlit application:
```bash
uv run -- streamlit run streamlit_new.py
```

Then open your browser at the URL provided by Streamlit (typically http://localhost:8501) and:
1. Enter the MCP Server URL (default: http://localhost:8000/sse)
2. Enter a Wikipedia article URL
3. Click "Fetch and Summarize Article"

## Components

### ollama_server.py
Implements the MCP server with a tool for summarizing Wikipedia articles. It fetches article content, converts it to markdown, and uses Ollama to generate a summary.

### updated_client.py
A command-line client that connects to the MCP server and calls the summarize_wikipedia_article tool.

### streamlit_new.py
A Streamlit-based web interface that provides a user-friendly way to interact with the MCP server.

## License

MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
