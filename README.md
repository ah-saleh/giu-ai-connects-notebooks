# GIU AI Connects — notebooks

One notebook per day, built together in the room. All on **LangChain v1** —
`create_agent` at the center, everything else an argument you add to it.

| Day | Notebook | What you build |
|---|---|---|
| — | `00-warmup-first-calls.ipynb` | Warm-up: plain `ChatAnthropic` calls — replies, tokens, temperature, streaming. Run it once to verify your setup |
| Tue | `day2-build-an-agent.ipynb` | The smallest agent → messages → `system_prompt` dial → `tools` (+ the round trip once by hand) → `response_format` → workflow vs agent |
| Wed | `day3-production-machinery.ipynb` | Skills + **your own SkillsMiddleware** (then the deepagents reveal), HITL middleware, checkpointers (SQLite), the sandbox lesson, an MCP server + client, a subagent behind a tool |
| Thu | `day4-agents-in-action.ipynb` | A complete triage mini-system + an eval suite that proves it works |

## Setup (once, with uv)

```bash
git clone https://github.com/ah-saleh/giu-ai-connects-notebooks.git
cd giu-ai-connects-notebooks
uv sync                 # creates .venv and installs everything
uv run jupyter lab      # start Jupyter inside the environment
```

Copy the key template and fill in your API key:

```bash
cp .env.example .env      # then edit .env and paste your key
```

Using another provider? Put its key in `.env` (e.g. `OPENAI_API_KEY`) and change
one line in the setup cell — the `MODEL` string, e.g. `"openai:gpt-4.1"`.
Everything else is identical; that is the point of the harness.

## Rules of the room

- Run top to bottom; cells marked **Your turn** are yours.
- When output surprises you, don't rerun it — **read the trace first**.
- Friday is office hours: bring what you built, especially the broken parts.
