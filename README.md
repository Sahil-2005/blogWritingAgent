# Blog Writing Agent (BWA)

A sophisticated AI-powered agent designed to research, plan, write, and illustrate high-quality blog posts. This project leverages **LangGraph** for orchestration, **OpenAI** for generation, **Tavily** for research, and **Streamlit** for the user interface.

## 🚀 Features

- **Intelligent Planning**: Breaks down blog topics into structured tasks and outlines.
- **Deep Research**: Uses Tavily Search API to gather up-to-date information and citations.
- **Agentic Workflow**: distinct roles for planning, researching, writing, and reviewing content.
- **Image Generation**: Automatically suggests and generates relevant images for the blog post.
- **Interactive UI**: Clean Streamlit interface for generating and downloading blogs (Markdown + Images).
- **Progressive Development**: Includes a series of notebooks demonstrating the evolution of the agent from basic to advanced.

## 📂 Project Structure

### Application
- **`bwa_backend.py`**: The core logic containing the LangGraph state machine, Pydantic models, and agent definitions.
- **`bwa_frontend.py`**: The Streamlit web application that serves as the user interface.

### Development Notebooks (Step-by-Step)
1. **`1_bwa_basic.ipynb`**: Initial basic implementation of the writing agent.
2. **`2_bwa_improved_prompting.ipynb`**: Enhancements to prompt engineering for better output quality.
3. **`3_bwa_research.ipynb`**: Integration of the research agent using Tavily.
4. **`4_bwa_research_fine_tuned.ipynb`**: Advanced research techniques and fine-tuning experiments.
5. **`5_bwa_image.ipynb`**: Implementation of image generation capabilities.

Other files:
- `tavily_test.ipynb`: Sandbox for testing search API capabilities.

## 🛠️ Setup & Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd blog-writing-agent
   ```

2. **Install Dependencies**
   Ensure you have Python 3.9+ installed.
   ```bash
   pip install langchain langchain-openai langgraph streamlit pydantic python-dotenv tavily-python pandas
   ```

3. **Environment Configuration**
   Create a `.env` file in the root directory and add your API keys:
   ```env
   OPENAI_API_KEY=sk-...
   TAVILY_API_KEY=tvly-...
   ```

##  ▶️ Usage

### Running the Web App
To start the full-featured application interface:
```bash
streamlit run bwa_frontend.py
```
This will open a local web server (usually at `http://localhost:8501`) where you can enter a topic and generate a complete blog post.

### Development & Experimentation
You can run the Jupyter notebooks to explore specific features or the evolution of the project:
```bash
jupyter notebook
```

## 🧩 Architecture

The agent functions as a graph of interconnected nodes:
1. **Router**: Analyzes the request and directs the flow.
2. **Planner**: Creates a comprehensive outline and determines research needs.
3. **Researcher**: (Optional) Gathers external information if required.
4. **Orchestrator**: Manages the delegation of writing tasks.
5. **Workers**: Generate content for specific sections of the blog.
6. **Reducer/Image Generator**: Compiles the drafts and generates accompanying visuals.

## 📄 License
[MIT](LICENSE)
