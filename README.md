<p align="center"><strong>VOIDSTACK LABS</strong> · AI RESEARCH & ENGINEERING</p>

# AI Interview Coach

A Python command-line prototype that uses a large language model to act as a technical interviewer. It asks one focused question at a time and uses conversation history to make follow-up questions more coherent.

## Features

- Interactive terminal-based interview loop.
- Configurable interview type, seniority level, and focus area.
- System prompt designed for focused technical interviews.
- In-memory conversation history separated by session ID.
- OpenRouter-hosted chat model integration through LangChain.

## Architecture

\`\`\`text
main.py
  |
  v
create_interviewer_with_history()
  |
  +--> ChatPromptTemplate
  |      - interviewer system prompt
  |      - conversation history
  |      - current user input
  |
  +--> ChatOpenRouter
  |
  +--> StrOutputParser
  |
  v
RunnableWithMessageHistory
  |
  v
Terminal response
\`\`\`

The current example configures a technical Python interview focused on Python fundamentals and design patterns. Conversation history is stored in process memory and is not persistent across application restarts.

## Technology

- Python
- LangChain Core and LangChain
- LangChain OpenRouter integration
- OpenRouter model API
- python-dotenv

## Getting started

Clone the repository:

\`\`\`bash
git clone https://github.com/VoidStackLabs/AI-Interview-Coach.git
cd AI-Interview-Coach
python -m venv .venv
\`\`\`

Activate the environment:

Windows PowerShell:
\`\`\`powershell
.\\.venv\\Scripts\\Activate.ps1
\`\`\`

macOS/Linux:
\`\`\`bash
source .venv/bin/activate
\`\`\`

Install dependencies:

\`\`\`bash
pip install -r requirements.txt
\`\`\`

Create a local .env file and add your OpenRouter API key:

\`\`\`env
OPENROUTER_API_KEY=your_api_key_here
\`\`\`

Keep this file private. Never commit API keys or other secrets to GitHub.

Run the application:

\`\`\`bash
python main.py
\`\`\`

Type \`quit\` to end the interview session.

## Configuration

The interview settings are currently defined in main.py:

- \`interview_type\`: interview category
- \`level\`: target position level
- \`focus_area\`: subject area for the interview
- \`session_id\`: identifier used to retrieve conversation history

Edit these values to experiment with different interview scenarios.

## Current limitations

- This is a learning prototype, not a production interview or assessment platform.
- Conversation history is in-memory and is lost when the process exits.
- Model identifiers and provider availability depend on the OpenRouter account and current API support.
- The current CLI flow has no web interface, authentication, persistent database, or automated evaluation pipeline.

## Roadmap

- [ ] Move interview settings into a configuration file or command-line arguments.
- [ ] Add persistent session storage.
- [ ] Add structured interview feedback with transparent evaluation criteria.
- [ ] Add tests for prompt construction and session-history behavior.
- [ ] Consider a web interface after the core interview workflow is stable.

---

<p align="center"><strong>VOIDSTACK LABS</strong> · BUILDING INTELLIGENT SYSTEMS.</p>
