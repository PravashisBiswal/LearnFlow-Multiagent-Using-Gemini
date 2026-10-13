# LearnFlow AI — Multi-Agent Learning Assistant

A team of 5 AI agents that research a topic, explain it step by step, simplify it, write student-style notes, and create practice questions.

> Add a screenshot of the output here: `![Demo](assets/demo.png)`

## Problem
Learning a new topic usually means searching, reading, simplifying, taking notes, and testing yourself. LearnFlow AI automates this whole flow with specialised agents that work one after another.

## How it works

```
Topic
  │
  ▼
Researcher ──► Teacher ──► Simplifier ──► Student ──► Examiner
(web search)  (step-by-step) (easy language) (short notes) (3 questions)
```

| Agent | Role |
|---|---|
| Researcher | Searches the web (Serper) and finds 3 important points |
| Teacher | Explains the topic step by step with examples |
| Simplifier | Rewrites the explanation in very simple language |
| Student | Writes short notes like a learner |
| Examiner | Creates 3 easy practice questions |

The five tasks run in a **sequential workflow**, so each agent builds on the previous output. The crew is started asynchronously with `kickoff_async()`.

## Tech Stack
Python, CrewAI, Gemini (via LiteLLM), Serper API (`SerperDevTool`)

## Features
- 5 agents with clear roles, goals and backstories
- Real-time web search tool for the Researcher agent
- Sequential 5-task workflow
- Asynchronous execution with `kickoff_async()`
- Change one variable (`topic`) to learn anything

## Example
Set the topic in the notebook:
```python
topic = "What is Artificial Intelligence"
```
Run the notebook and the crew prints the research points, explanation, simple version, notes, and questions.

## How to Run

1. Clone the repo
   ```bash
   git clone https://github.com/PravashisBiswal/LearnFlow-Multiagent-Using-Gemini.git
   cd LearnFlow-Multiagent-Using-Gemini
   ```
2. Install packages
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file (copy `.env.example`) and add your own keys
   ```
   GEMINI_API_KEY=your_gemini_key
   SERPER_API_KEY=your_serper_key
   ```
4. Open `LearnFlow_AI_Multiagent_Gemini.ipynb` in Jupyter or Google Colab and run all cells.

> The notebook uses top-level `await`, which works in Jupyter, Colab and Kaggle. In a normal `.py` file use `asyncio.run(...)`.
> Never commit your `.env` file or API keys.

## Limitations and Future Improvements
- Runs from a notebook; move to a clean `app.py` with a Gradio or Streamlit interface
- Let the user type the topic instead of editing code
- Add memory and a quiz-checking step that grades the student's answers
- Add tracing (LangSmith or Langfuse) and cost/latency tracking
- Compare the multi-agent flow with a single-agent baseline

## Links
- Demo Video: [https://www.linkedin.com/posts/pravashisbiswal_generativeai-agenticai-crewai-activity-7514661791667257344-vrLK?utm_source=share&utm_medium=member_desktop&rcm=ACoAADkWWUYB5cnJ2PJLirJ_0r0TqPUtBV19K7w]

## Author
Pravashis Biswal — [LinkedIn](https://www.linkedin.com/in/pravashisbiswal) · [GitHub](https://github.com/pravashisbiswal)
