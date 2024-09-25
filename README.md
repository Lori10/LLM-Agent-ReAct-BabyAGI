# Autonomous AI Research Agent Based on ReAct

This repository consists of two autonomous AI agents: 
1. **BabyAGI Agent**
2. **ReAct Agent**

Since both agents utilize similar tools, they are included in the same repository.

---

## 1. BabyAGI Agent

### Project Summary
The BabyAGI Agent is designed to autonomously generate factual answers with references, based on research publications. The agent operates through three distinct LLMs (Task Generation LLM, Task Execution LLM, and Task Prioritization LLM), functioning as follows:

0. **Task Generation LLM**: The Task Generation LLM generates a task list needed to reach the objective or answer the original question.
1. **Task Execution LLM**: The agent pulls the first task from the task list. The Task Execution LLM uses OpenAI's API to complete the task based on the context, enriches the result, and stores it in Chroma or Weaviate.
3. **Task Prioritization LLM**: The Task Creation LLM updates the task list by creating new tasks and the Task Prioritization LLM reprioritizes them based on the objective and the results of previous tasks.

### Key Features
- Extends the open-source BabyAGI implementation by adding an **Answer Generation LLM** to generate a final answer for the original question or objective.
- Optimizes bugs related to task generation.
- The Task Execution LLM extracts relevant research papers from databases such as **arXiv, ChemRxiv, PubMed**, and more through API requests.
- Conducts semantic searches on extracted papers to identify the most relevant information, which is used as context for the GPT-3.5-turbo model to generate accurate and factual responses.
- The Answer Generation LLM provides the final output, including the answer and the reference paper upon which the answer is based.
- Outputs are formatted in **JSON**, facilitating the extraction of necessary details like answers and references, enhancing usability and integration.

### Tools and Packages
- **Python**, **langchain**, **paperqa**, **findpapers**, **unpaywall**

### Related Code/Scripts
- The following Python scripts are relevant to this agent:
  - `scriptA.py`
  - `scriptB.py`

---

## 2. ReAct Agent

### Project Summary
The ReAct Agent is built on ReAct logic, which integrates reasoning and acting into a unified method. This agent autonomously generates factual answers with references based on research publications. ReAct leverages advances in language models that support reasoning (e.g., chain-of-thought prompting) and acting (e.g., WebGPT, SayCan, ACT-1), improving overall capabilities.

### Key Features
- The agent performs multi-step self-questioning and answering until it can confidently answer the original question.
- It utilizies a tool that helps answer sub-questions.
- For each sub-question, the tool extracts relevant research papers from databases like **arXiv, ChemRxiv, PubMed**, and others through API requests.
- Conducts semantic searches on extracted papers to identify the most relevant information, which is used as context for the GPT-3.5-turbo model to generate accurate and factual responses.
- The final output includes both the answer and the reference paper upon which the answer was generated.
- Outputs are in **JSON** format, simplifying the extraction of details such as answers and references, enhancing usability and integration.

### Tools and Packages
- **Python**, **langchain**, **paperqa**, **findpapers**, **unpaywall**

---
