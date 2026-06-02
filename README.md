# AI Engineering Hackathon: Quick Reference

*Last updated: June 2, 2026 — AI tools move fast. Free tiers, links, and model names change often, so some details below may be out of date.*

3 hours. Build something interesting. Have something to show.

Pick what fits from the menus below. Combine freely. New to coding on Windows? Start with **Getting set up** just below.

---

## Getting set up: Python & VS Code on Windows

New to this? Here's the shortest path from a blank Windows machine to running Python. Microsoft's official walkthrough covers it end to end: [Get started using Python on Windows for beginners](https://learn.microsoft.com/en-us/windows/dev-environment/python?tabs=winget).

The essentials:

1. **Install Python** — in PowerShell, run `winget install Python.Python.3.12`, or download it from [python.org/downloads](https://www.python.org/downloads/) (in the installer, tick "Add Python to PATH"). Verify with `python --version`.
2. **Install VS Code** — Microsoft's free code editor: [code.visualstudio.com/download](https://code.visualstudio.com/download) (or run `winget install Microsoft.VisualStudioCode`).
3. **Add the Python extension** — in VS Code, press `Ctrl+Shift+X`, search "Python," and install the one published by Microsoft. You get run buttons, autocomplete, and a debugger.
4. **Install libraries** with pip as you need them, e.g. `pip install requests pandas`. See **Common Python libraries** below for the ones worth knowing about.

> Tip: keep each project's packages isolated with a virtual environment — run `python -m venv .venv`, then `.\.venv\Scripts\Activate.ps1` in PowerShell. Optional for a 3-hour hack, but it keeps things tidy.

---

## LLM access: programmatic (write code that calls a model)

| Tool | Good for | Example |
|------|----------|---------|
| [Anthropic SDK](https://pypi.org/project/anthropic/) (`anthropic` Python pkg) | A Python library you `pip install` that lets your program send prompts to Claude and get responses back. Needs an API key (paid, per token used). | Build a Streamlit app that uses Claude to answer questions about a PDF you uploaded |
| [OpenAI SDK](https://pypi.org/project/openai/) (`openai` Python pkg) | Same idea but for OpenAI models (GPT-4o, GPT-4o-mini). Free trial credits to start, then pay per use. | Script that summarizes your meeting notes into action items |
| [Google AI Studio + Gemini API](https://aistudio.google.com) | Free tier access to Gemini models with no credit card required. Generous daily limits for hackathon use. Has a Python SDK. | Power your app with Gemini's free tier so you don't burn through paid credits |
| [Groq API](https://console.groq.com) (free) | Free tier with extremely fast inference (low latency) for open models like Llama 3 and Mixtral. OpenAI-compatible SDK so existing examples mostly just work. | A chat app where you want responses to feel instant |
| [Hugging Face Inference API](https://huggingface.co/docs/api-inference) (free) | Free hosted endpoints for thousands of open-source models. Slower than commercial APIs but no card needed. | Try a niche community model (e.g. a sentiment classifier) without setting it up yourself |
| [OpenRouter](https://openrouter.ai) (free models) | One API key gets you access to a catalog of models, including free open ones like Llama and Mistral variants. | A/B test the same prompt across a few different free models from one place |

## LLM access: chat (type in a browser)

| Tool | Good for | Example |
|------|----------|---------|
| [Claude Desktop](https://claude.ai/download) (Code + Cowork tabs) | Your assigned tool for the hack. Code tab is a pair-programmer that can run code; Cowork tab handles files and desktop tasks. | Have Claude write your Streamlit app and execute it in the Code tab to test |
| [Claude.ai](https://claude.ai) (free tier) | Web chat with Claude. Good for thinking out loud, drafting text, asking questions. | Drafting your demo script or README copy |
| [ChatGPT](https://chatgpt.com) (free tier) | Web chat with GPT. Free tier includes image gen and web search. | Get a second opinion or a different framing on an idea |
| [Gemini](https://gemini.google.com) (free tier) | Google's chat assistant. Plugs into Google Docs, Sheets, Gmail. | Brainstorm copy or pull context from a Google Doc |
| [Microsoft Copilot](https://copilot.microsoft.com) (free) | Bing-powered chat with image gen built in. | Quick research questions with web search included |

## Image generation (free)

| Tool | Good for | Example |
|------|----------|---------|
| [Microsoft Copilot Designer / Bing Image Creator](https://www.bing.com/images/create) | Free DALL-E 3 access in the browser. Sign in with a Microsoft account, generate, download. | Hero image for your demo slide deck |
| [Gemini (image generation)](https://gemini.google.com) | Image generation built into Gemini chat. Free tier. | Quick illustration or logo concept |
| [Hugging Face Spaces](https://huggingface.co/spaces) (Stable Diffusion, FLUX, etc.) | Free, in-browser image generation using community models. Huge variety of styles. | Try a specific art style (e.g. retro pixel art) not in commercial tools |
| [Ideogram](https://ideogram.ai) (free tier) | Particularly good at images with readable text inside them. | A demo poster that includes your project tagline |
| [Leonardo AI](https://leonardo.ai) (free tier) | Daily free token allotment, leans toward game-art and illustration styles. | Concept art for a game-style or character-driven demo |

## Free compute & hosting

| Tool | Good for | Example |
|------|----------|---------|
| [Google Colab](https://colab.research.google.com) (free) | Cloud Jupyter notebooks with free CPU and limited free GPU time. Run Python in a browser with no install. | Run a machine-learning script that needs more compute than your laptop has |
| [Kaggle Notebooks](https://www.kaggle.com/code) (free) | Similar to Colab. Free GPU hours and a built-in library of datasets. | Train or test a model against a public dataset without downloading anything |
| [Hugging Face Spaces](https://huggingface.co/spaces) (free) | Free hosting for a small web app or ML demo. Push your Gradio/Streamlit app and get a public link. | Put your finished demo online so judges can click a link instead of watching your screen |
| [Streamlit Community Cloud](https://streamlit.io/cloud) (free) | One-click free hosting for Streamlit apps straight from a GitHub repo. | Share your Streamlit app as a live URL during the demo |

## Helper libraries, SDKs & builders

| Tool | Good for | Example |
|------|----------|---------|
| [Microsoft Copilot Studio](https://copilotstudio.microsoft.com) (low-code, no programming required) | A point-and-click way to build a custom AI agent or chatbot. Connect it to your own documents and data, then publish it to Teams, SharePoint, or a webpage. Likely available through the Microsoft 365 account you already have. | Build an assistant that answers questions from a folder of documents, then drop it into Teams for your demo |
| [`langchain`](https://python.langchain.com) / [`llama-index`](https://docs.llamaindex.ai) (Python) | Pre-built abstractions for chains, retrieval, and agents. Saves wiring time at the cost of a learning curve. | Build a retrieval-augmented Q&A app with less manual plumbing |
| [Vercel AI SDK](https://ai-sdk.dev) (JavaScript / TypeScript) | A free, open-source toolkit for building LLM apps in JS/TS. One unified API across providers (Claude, GPT, Gemini), with streaming and tool calling built in. | Build a Next.js chat app that streams responses and can swap models with one line |
| [LangGraph](https://www.langchain.com/langgraph) (Python / JavaScript) | A framework for building agent workflows: you map out the steps and decisions an agent moves through, and it handles the looping, tool calls, and state along the way. More control than a plain chain, but more setup too. | Build a research agent that decides at each step whether to search, read, or answer |

## Common Python libraries

Basic, everyday building blocks you'll reach for in almost any Python project. Install with `pip install <name>`.

| Library | Good for | Example |
|---------|----------|---------|
| [`requests`](https://requests.readthedocs.io) | The standard way to call a REST API or fetch a web page from Python — `GET`/`POST`, headers, and JSON in a few lines. | Pull live data from a public API (weather, stocks, sports) to feed into your app |
| [`pandas`](https://pandas.pydata.org) | Load, clean, filter, and summarize tabular data (CSV, Excel, JSON). The workhorse for anything spreadsheet-shaped. | Read a messy CSV, group and total it, and show the result in your demo |
| [`python-dotenv`](https://pypi.org/project/python-dotenv/) | Load secrets like API keys from a `.env` file instead of hard-coding them — keeps keys out of your code and out of git. | Keep `ANTHROPIC_API_KEY` in `.env` and read it with `os.getenv` |
| [`matplotlib`](https://matplotlib.org) / [`plotly`](https://plotly.com/python/) | Turn numbers into charts. matplotlib is the classic; plotly makes interactive ones. | Plot a trend line or bar chart straight from your pandas data |
| [`numpy`](https://numpy.org) | Fast math over arrays of numbers — the foundation most data and ML libraries are built on. | Crunch a big list of numbers without slow Python loops |
| [`beautifulsoup4`](https://www.crummy.com/software/BeautifulSoup/) | Parse and pull data out of HTML — i.e. scrape a page after you fetch it with `requests`. | Grab the headlines off a news page, then summarize them with an LLM |
| [`Pillow`](https://python-pillow.org) | Open, resize, crop, and convert images (imported as `PIL`). | Resize user-uploaded images before sending them to a vision model |
| [`pydantic`](https://docs.pydantic.dev) | Define the exact shape of your data and validate it automatically — pairs naturally with LLM "structured output." | Make the model return JSON that matches a `User` schema you defined |

## UI / front-end

| Tool | Good for | Example |
|------|----------|---------|
| [Streamlit](https://streamlit.io) | The fastest way to turn a Python script into a web UI. Add a slider, a file uploader, a chart in one line each. | Build a chat interface where users upload a CSV and ask questions about it |
| [Gradio](https://gradio.app) | Similar idea to Streamlit, widely used for ML demos. Plays especially well with Hugging Face Spaces. | A demo where users drag in an image and your model classifies it |
| HTML / CSS / JS (single file) | A static webpage you can open in a browser. Maximum visual control, no Python needed. | A landing page or visualization with custom styling |
| [Jupyter notebook](https://jupyter.org) | A document that mixes code, output, and prose. Good when the *story* is the analysis. | Walk through how your model came up with a recommendation, with charts inline |
| PowerPoint / slide deck | A presentation. Completely legitimate output, especially for concept-heavy demos. | A 5-slide pitch with screenshots of a working prototype |

## LLM patterns

| Pattern | Good for | Example |
|---------|----------|---------|
| Direct API call | The simplest possible LLM integration: one prompt in, one response out. | Generate a summary, translate text, classify a piece of input |
| Multi-turn chat | The model remembers earlier messages in the same conversation (because you send them all each time). | A chatbot that knows what the user said five turns ago |
| Doc Q&A via context window | Paste a whole document into the system prompt and ask questions about it. No vector database needed. | "Answer questions about this 30-page handbook I just dropped in" |
| Tool use (function calling) | Define functions and let the model decide when to call them. The model picks the tool and arguments. | The model calls your `get_weather(city)` function when the user asks about weather |
| Agent loop | The model picks a tool, sees the result, picks another, and iterates until done. | A research assistant that searches, reads, summarizes, and writes a report on its own |
| MCP server | A standard way to expose your tools to Claude Desktop and other LLM clients. | Wrap your project's actions as MCP tools so Claude can use them in the Code tab |

## Data & persistence

| Tool | Good for | Example |
|------|----------|---------|
| CSV / JSON files | File-based data, easy to view, edit by hand, and commit to git. Zero setup. | Save user responses to `responses.csv` as they come in |
| In-memory `dict` / `list` | Variables in your running program. Fastest possible, but data is lost when the program stops. | Track session state during a single demo run |
| [SQLite](https://www.sqlite.org) | A real SQL database in a single file. No server to run, ships with Python. | Store and query structured data that needs to survive a restart |
| [Chroma](https://www.trychroma.com) / [FAISS](https://github.com/facebookresearch/faiss) (vector store) | Store text as embeddings so you can search by meaning, not just keywords. The backbone of RAG. | Find the most relevant chunks of a document to feed into a prompt |
