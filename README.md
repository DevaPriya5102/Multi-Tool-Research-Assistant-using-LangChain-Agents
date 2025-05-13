
# Multi-Tool Research Assistant using LangChain Agents

## Project Overview

This project demonstrates the creation of an AI-powered research assistant using LangChain's tools and agent framework. The assistant integrates multiple research and retrieval tools, including Arxiv, Wikipedia, and a custom retrieval-augmented generation (RAG) component built from web data. It is designed to respond intelligently to user queries by dynamically selecting the most relevant tool and generating a thoughtful, informed answer.

## What I Built

I developed a research assistant that uses a function-calling agent to access three distinct tools:

1. Wikipedia tool for retrieving short encyclopedic information.
2. Arxiv tool for querying academic articles.
3. A custom RAG tool that fetches and summarizes web data from a Goodreads book page using document splitting, embedding generation, and FAISS vector storage.

All tools are integrated into a LangChain agent powered by OpenAI's GPT-4 model.

## Tools and Technologies Used

- LangChain
- LangChain Community Tools (WikipediaQueryRun, ArxivQueryRun, WebBaseLoader)
- RecursiveCharacterTextSplitter
- OpenAIEmbeddings
- FAISS Vector Store
- OpenAI GPT-4 via LangChain
- LangChain Hub
- Python dotenv
- Jupyter Notebook

## Process Explanation

### Step 1: Tool Creation

- Used WikipediaAPIWrapper and ArxivAPIWrapper for structured tool access.
- Limited results and content size for clean, focused responses.

### Step 2: Custom RAG Tool

- Scraped a Goodreads book description.
- Split content into chunks.
- Generated semantic embeddings using OpenAI.
- Stored and searched vector data using FAISS.
- Created a retriever tool from this pipeline.

### Step 3: Agent Setup

- Pulled a function-calling prompt from LangChain Hub.
- Used create_openai_tools_agent to create the agent.

### Step 4: Agent Execution

- Initialized AgentExecutor.
- Queried the assistant with a sample input like "Difference between enterprise and startup".

## Final Outcome

The final result is a modular, multi-source intelligent agent capable of dynamic tool selection and smart data-driven responses to user queries.

## Use Cases

- Research automation
- Educational assistance
- Knowledge base querying
- Multi-source contextual information retrieval


## Installation

1. Clone the repository:

```bash
git clone https://github.com/DevaPriya5102/Multi-Tool-Research-Assistant-using-LangChain-Agents.git
cd Multi-Tool-Research-Assistant-using-LangChain-Agents
```

2. Create a virtual environment and activate it:

```bash
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
```

3. Install the dependencies:

```bash
pip install -r requirements.txt
```

4. Set your `.env` file with:

```
OPENAI_API_KEY=your_openai_api_key
GROQ_API_KEY=your_groq_api_key
```

## Usage

Open the notebook or script and run each section. Try modifying the input prompt to ask different research questions.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.
