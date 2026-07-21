# GIU AI Connects — notebooks

One notebook per day, built together in the room. All on **LangChain v1** —
`create_agent` at the center, everything else an argument you add to it.

| Day | Notebook | What you build |
|---|---|---|
| — | `00-warmup-first-calls.ipynb` | Warm-up: plain `ChatAnthropic` calls — replies, tokens, temperature, streaming. Run it once to verify your setup |
| Tue | `day2-build-an-agent.ipynb` | The smallest agent → messages → `system_prompt` dial → `tools` (+ the round trip once by hand) → `response_format` → workflow vs agent |
| Wed | `day3a-middleware.ipynb` | The six hooks around the loop; summarization that keeps the context window honest; **write your own ToolBudgetMiddleware** |
| Wed | `day3b-human-in-the-loop.ipynb` | Checkpointers and `thread_id` (SQLite survives a restart); the run **pauses** before a write and resumes with `Command(resume=…)` |
| Wed | `day3c-skills.ipynb` | Skill folders with a `SKILL.md` contract, the injector middleware, the deepagents reveal — then **author a skill yourself** |
| Wed | `day3d-backends-and-sandboxes.ipynb` | Why restricted `eval` is not a sandbox; virtual files vs a real `workspace/` folder — deciding where the agent's work lands |
| Thu | `day4a-mcp-and-subagents.ipynb` | A real **MCP server** + client, then a subagent behind one `@tool` — and a guarded MCP write that uses everything from Wednesday |
| Thu | `day4b-triage-and-evals.ipynb` | A complete triage mini-system + an eval suite that proves it works |

Wednesday and Thursday run as short sessions: slides, a live demo, then one
notebook each. The last section of every notebook is **your** task.

## Setup (once)

```bash
git clone https://github.com/ah-saleh/giu-ai-connects-notebooks.git
cd giu-ai-connects-notebooks

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

(Python 3.11 or newer. Have [uv](https://docs.astral.sh/uv/)? Then just
`uv sync && uv run jupyter lab` instead — same environment, faster.)

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
