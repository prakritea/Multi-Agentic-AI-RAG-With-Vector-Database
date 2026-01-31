## Multi-Agentic AI RAG with Vector Database

A multi-agent AI system that can read, search, and summarize PDFs using retrieval-augmented generation (RAG) and a Postgres + pgvector vector database.
It supports CLI interactions with a PDF knowledge base and leverages modern Python tools like phi, Typer, and dotenv.

# Features

PDF Knowledge Base: Automatically loads PDFs from URLs.

Vector Database Search: Uses Postgres + pgvector to store embeddings for fast semantic search.

Multi-Agent AI: Combines multiple AI agents for searching, summarizing, and answering queries.

CLI Assistant: Interact via a clean command-line interface.

Session Persistence: Stores past runs and knowledge for each user.

# Tech Stack

Python 3.11+

phi
 AI framework

Typer
 CLI framework

PostgreSQL + pgvector
 for vector embeddings

dotenv for environment variables

Pydantic for type-safe data models

# Project Structure
Multi-Agentic-AI-RAG-With-Vector-Database/
│
├─ myenv/                  # Python virtual environment
├─ app.py                  # Main CLI entrypoint for PDF assistant
├─ requirements.txt        # Python dependencies
├─ .env                    # Environment variables (API keys, DB credentials)
├─ knowledge_base/         # PDF URL knowledge base
└─ README.md               # Project documentation

Prerequisites

Python 3.11+ installed

PostgreSQL running locally or remotely

pgvector extension installed in PostgreSQL

An API key for GPT-based AI (stored in .env)

# Setup Instructions

Clone the repository

git clone https://github.com/yourusername/Multi-Agentic-AI-RAG-With-Vector-Database.git
cd Multi-Agentic-AI-RAG-With-Vector-Database


Create and activate a virtual environment

python3 -m venv myenv
source myenv/bin/activate


Install dependencies

pip install --upgrade pip
pip install -r requirements.txt


Set environment variables

Create a .env file in the project root:

GROQ_API_KEY=your_api_key_here
DB_URL=postgresql+psycopg://username:password@localhost:5432/ai


Run the PDF assistant

python app.py


Follow the prompts to start a new session or continue an existing one.

Usage

Start a new session

python app.py --new True --user alice


Continue an existing session

python app.py --user alice


Interact with the assistant
The CLI supports Markdown-style output and shows AI tool calls.

How It Works

Loads PDF(s) from URL(s) and generates embeddings.

Stores embeddings in PostgreSQL + pgvector.

Uses AI agents to search, summarize, and answer queries.

Maintains session state in the database for continued interactions.