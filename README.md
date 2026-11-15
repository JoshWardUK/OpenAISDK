OpenAI Agents SDK Learning Examples
A collection of Python notebooks exploring the OpenAI Agents SDK through practical examples, including Formula 1 reporting, research workflows, sales email generation, human approval and sandbox execution.

The notebooks cover function tools, streaming, conversation memory, structured outputs, agent orchestration and using models through OpenRouter.
Notebooks
Notebook	What it explores
[Streaming, Tools & Memory](Streaming%2CTools%26Memory.ipynb)	Running agents, streaming responses, a hotel greeting function tool, tracing and conversation history with SQLiteSession.
[Agentic AI Tools](AgenticAITools.ipynb)	Retrieving F1 data from Jolpica, paginating lap timings, reading and writing CSV files, generating Markdown race reports and delegating article writing.
[Orchestrating by LLMs](OrchestratingByLLMs.ipynb)	Exposing three sales agents with as_tool() so a manager agent can request and evaluate email drafts.
[Structured Outputs & Guardrails](StructuredOutputs%26Guardrails.ipynb)	Pydantic output schemas, reviewing email quality, defining an output guardrail and manually checking a generated email.
[Human in the Loop](HumanInTheLoop.ipynb)	Requesting approval for a tool call, saving paused run state and resuming after approval or rejection.
[OpenRouter](OpenRouter.ipynb)	Using an OpenAI-compatible client to run Gemini, Kimi and Claude agents through OpenRouter.
[Sandbox Agents](SandboxAgents.ipynb)	Giving an engineering agent a local code workspace and an output directory for bug fixes.
[Deep Research](DeepResearch.ipynb)	Planning searches, running web research concurrently, producing a structured report and saving Markdown after a review.


Setup
Use a Python environment compatible with the installed Agents SDK. Python 3.12 is a suggested starting point. Dependencies are currently unpinned.

Clone the repository and create a virtual environment:
git clone https://github.com/JoshWardUK/OpenAISDK.git
cd OpenAISDK

python3 -m venv .venv
source .venv/bin/activate

python -m pip install --upgrade pip
python -m pip install openai-agents openai python-dotenv pydantic requests pandas jupyterlab ipykernel graphviz
On Windows, activate the environment with .venv\Scripts\activate in Command Prompt.

Register the environment as a notebook kernel:
python -m ipykernel install --user --name openaisdk --display-name "Python (OpenAISDK)"
The Graphviz Python package supports the visualization import in the orchestration notebook. Rendering agent graphs also requires the Graphviz system application.
API keys
Create a .env file in the repository root:
OPENAI_API_KEY=your_openai_api_key
OPENROUTER_API_KEY=your_openrouter_api_key
- OpenAI examples use OPENAI_API_KEY.
- OpenRouter examples use OPENROUTER_API_KEY.
- The deep research notebook uses both providers.
- The notebooks load these variables using load_dotenv(override=True).
Keep real credentials out of commits and clear notebook outputs containing credentials before sharing. Model calls and hosted web searches can incur provider charges.