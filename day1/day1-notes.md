## Day 1 Personal Notes

### Whitepaper: Introduction to Agents

- **Paradigm shift:** Moving from predictive AI toward autonomous agents capable of planning, acting, and iterating without constant human direction.
- **Core anatomy:** Successful agents combine a reasoning **model** (“brain”), actionable **tools** (“hands”), an **orchestration layer** (“nervous system”), and deployment/runtime services (“body”).
- **Five-step loop:** Mission → Scan the scene → Think → Act → Observe & iterate. This loop underpins all task execution.
- **Capability levels:** 
  - *Level 0* – standalone LM reasoning.
  - *Level 1* – tool-augmented problem solver.
  - *Level 2* – strategic planner with context engineering.
  - *Level 3* – coordinated multi-agent teams.
  - *Level 4* – self-evolving systems that create new tools/agents.
- **Design focus:** Context engineering, prompt/persona design, and precise tool contracts are critical to reliability.
- **Agent Ops:** Treat evaluations like experiments; use LM-as-judge, traces (OpenTelemetry), and human feedback loops to maintain quality.
- **Security & governance:** Establish agent identity, least-privilege policies, guardrails, and a central control plane to prevent “agent sprawl.”
- **Evolution:** Leverage runtime feedback, simulations (“Agent Gym”), and learning agents to keep systems aligned with changing policies.
- **Case studies:** Google Co-Scientist (multi-agent research) and AlphaEvolve (evolutionary code discovery) illustrate advanced orchestration and continuous improvement.

### Notebook 1A: From Prompt to Action

- Walkthrough of configuring Gemini API secrets inside Kaggle and verifying with `UserSecretsClient`.
- Imports core ADK components: `Agent`, `InMemoryRunner`, `google_search`.
- Defines helper to surface the ADK Web UI proxy in Kaggle.
- Builds a `helpful_assistant` agent using Gemini 2.5 Flash Lite with Google Search tool.
- Uses `InMemoryRunner.run_debug` to:
  - Answer conceptual question about Google’s Agent Development Kit.
  - Demo real-time lookup (London weather) via tool invocation.
- Encourages experimentation through prompts requiring current information.
- Introduces ADK Web UI for interactive testing and debugging.

### Notebook 1B: Agent Architectures

- Reinforces multi-agent rationale: specialization beats monolithic prompts.
- Constructs **ResearchAgent** (Google Search) and **SummarizerAgent**, orchestrated by a coordinator via `AgentTool`.
- Demonstrates sequential workflows for predictable pipelines (outline → draft → edit).
- Highlights other orchestration patterns (parallel, loops) and the role of state (`output_key`) for passing results.
- Emphasizes clear instructions, structured outputs, and chaining agents to build resilient systems.

### Personal Takeaways & Next Steps

- Focus on mastering context engineering and tool contracts before attempting multi-agent systems.
- Instrument early: set up evaluation prompts and logging before scaling features.
- Security isn’t optional—even single-agent prototypes need identity, guardrails, and least-privilege access.
- Action items:
  - Replicate the `helpful_assistant` locally with environment variables instead of Kaggle secrets.
  - Draft a small multi-agent experiment (e.g., research + summarize) using local data sources.
  - Start a metrics log capturing latency, tool success rate, and qualitative feedback for each run.

