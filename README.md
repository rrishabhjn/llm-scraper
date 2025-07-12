# 🧠 llm-scraper

A lightweight CLI interface that combines LLM agents and browser automation to scrape dynamic web content using natural language commands.

This project uses [LangGraph](https://github.com/langchain-ai/langgraph), [Anthropic's Claude 3.5](https://docs.langchain.com/docs/integrations/chat/anthropic/), and [Bright Data MCP](https://brightdata.com/products/mcp) tools to build a fully agentic browser-based scraping agent.

---

## 🚀 Features

- 🌐 **JavaScript-aware scraping** via BrightData's MCP and headless Chrome
- 🧠 **LLM-powered reasoning** using Claude 3.5 Sonnet to interpret tasks and choose scraping tools
- 🧰 **LangGraph ReAct agent** orchestration for chaining tool use
- 🔧 **Extensible tool loading** using LangChain MCP adapters
- 🤖 **Conversational interface** — type queries like _"Extract the titles of the top Hacker News posts"_ and let the agent figure it out

---

## 📦 Installation

1. Clone the repo

```bash
git clone https://github.com/rrishabhjn/llm-scraper.git
cd llm-scraper
```

2. Install dependencies (Python ≥ 3.13)

```bash
pip install -r requirements.txt
# or, if you're using PEP 621:
uv pip install -r uv.lock
```

3. Set up environment variables

Create a `.env` file at the root of the project with the following values:

```env
API_TOKEN=your_brightdata_api_token
BROWSER_AUTH=your_browser_auth_string
WEB_UNLOCKER_ZONE=your_zone
```

---

## 🧪 Usage

Run the agent:

```bash
python main.py
```

Then simply type your queries like:

```text
You: Go to https://news.ycombinator.com and extract the top 5 post titles, authors, and points.
```

The agent will reason about the tools it needs, interact with the page via MCP, and return structured results.

---

## 🔍 Example Tech Stack

- `langgraph.prebuilt.create_react_agent` – Core LLM agent orchestration
- `ChatAnthropic` – Claude 3.5 LLM interface
- `BrightData MCP` – Headless browser interface
- `langchain_mcp_adapters` – Auto-loaded scraping tools

---

## 📁 Project Structure

```bash
.
├── main.py            # Entrypoint CLI chat loop
├── pyproject.toml     # Dependency and project metadata
├── .env               # API tokens and browser zone credentials
└── README.md          # You're reading it!
```

---

## 🤝 Contributions

This is a proof-of-concept, and contributions are welcome! Ideas for improvement:

- Add schema-based scraping using pydantic or Zod
- Plug in other LLM providers like GPT-4 or Gemini
- Create browser screenshots or download PDFs via tools

---

## 📄 License

MIT © Rishabh Jain

---

## 🙋‍♂️ Author

[Rishabh Jain](https://www.linkedin.com/in/rrishabhjn) – PM with a builder mindset. I work at the intersection of AI, automation, and developer tools.
