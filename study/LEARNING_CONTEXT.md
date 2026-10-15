# Learning Goal

I am systematically studying this repository in order to master AI Agent development.

My goal is not only to run the examples.

I want to become able to:

1. Explain the core architecture of an Agent.
2. Read an unfamiliar Agent project.
3. Trace data flow through an Agent.
4. Modify existing Agent implementations.
5. Implement simple Agents independently.
6. Understand Context, Tools, Memory, RAG, Evaluation and related concepts.

---

# Current Background

I have basic experience with:

- Python
- Git
- command line
- uv
- pyproject.toml
- HTTP APIs
- LLM usage
- basic AI-assisted coding

---

# Concepts I Already Understand

I currently understand the basics of:

- Python functions
- classes and objects
- list and dict
- basic type hints
- JSON
- HTTP request / response
- environment variables and `.env`
- LLM messages
- system / user / assistant roles
- Context Window
- Structured Output
- Tool Calling
- basic Agent Loop
- basic termination conditions

My current mental model of a Tool Calling Agent is:

User Input
→ Context
→ LLM
→ Tool Call
→ Controller
→ Tool
→ Tool Result
→ Context
→ LLM
→ Final Answer

I understand that:

- The LLM decides what action it wants to take.
- The Controller decides whether and how to execute that action.
- A Tool performs a concrete operation.
- Tool Results must be added back into Context before the LLM can use them.
- An Agent usually requires a loop rather than a single LLM call.

---

# Knowledge Gaps

Topics that I have not yet mastered include:

- Python exception handling
- async / await
- more advanced Python project structure
- Embeddings
- Vector Search
- RAG
- Memory
- Evaluation
- post-training
- more advanced Agent engineering

These should normally be learned when they become necessary in the book rather than studied all at once beforehand.

---

# Preferred Learning Method

For every experiment, prioritize understanding over code completion.

First help me answer:

1. What problem does this experiment solve?
2. Where is the Context?
3. Where is the LLM?
4. Where are the Tools?
5. Where is the Controller / Agent Loop?
6. How does data flow?
7. What makes the loop stop?

When possible:

- Ask me to predict behavior before running code.
- Explain unfamiliar prerequisite knowledge only when needed.
- Connect new ideas to concepts I already understand.
- Do not immediately give me exercise solutions.
- After an experiment works, give me a small modification to implement myself.
- At important milestones, ask me to explain the architecture in my own words.
