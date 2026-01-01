# 🤖 Autonomous AI Agent with Tool Calling

![n8n](https://img.shields.io/badge/Orchestration-n8n-FF6560?style=for-the-badge&logo=n8n&logoColor=white)
![Gemini](https://img.shields.io/badge/AI_Model-Gemini_2.5_Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Status](https://img.shields.io/badge/Status-Functional-brightgreen?style=for-the-badge)

## 📖 Project Overview
This repository contains an advanced **Agentic Workflow** built using **n8n**. Unlike standard chatbots that only generate text, this agent possesses **Multi-Step Reasoning** capabilities. It intelligently determines when to rely on its internal knowledge base versus when to execute external **Tools** (e.g., Calculator, Wikipedia Search) to solve complex, multi-layered queries.

## 🚀 Key Features
* **Decoupled Reasoning:** The agent autonomously decides the sequence of actions required to answer a query.
* **Tool Calling Architecture:** Seamlessly integrates with:
    * 🧮 **Calculator:** For precise mathematical computations.
    * 🌐 **Wikipedia:** For retrieving real-time factual information.
* **Contextual Memory:** Utilizes Window Buffer Memory to maintain conversation context across multiple turns.
* **Error Handling:** Built-in fallback mechanisms if a tool fails to execute.

## 📸 Workflow Architecture
> *Please refer to `workflow_screenshot.png` in the file list for the visual node structure.*

## 🛠️ Tech Stack
| Component | Technology | Description |
| :--- | :--- | :--- |
| **Orchestrator** | n8n (Self-hosted/Cloud) | Handles the logic flow and node connections. |
| **LLM Engine** | Google Gemini 2.5 Flash | Provides the reasoning capabilities and intent parsing. |
| **Tools** | Wikipedia API, MathJS | External execution environments. |
| **Interface** | Webhook / Chat Trigger | Entry point for user interaction. |

## 🔄 How It Works (The Logic)
1.  **Ingestion:** User submits a query via the Chat Interface (e.g., *"What is the age of the Tesla CEO multiplied by 2?"*).
2.  **Reasoning Loop:** The AI analyzes the prompt and breaks it down:
    * *Sub-task 1:* Find the CEO of Tesla and their birth year (Needs **Wikipedia**).
    * *Sub-task 2:* Calculate current age (Needs **Calculator**).
    * *Sub-task 3:* Multiply age by 2 (Needs **Calculator**).
3.  **Execution:** The agent calls the respective tools in sequence, passing data between them.
4.  **Synthesis:** The final result is formatted into a natural language response.

## 📦 How to Run
1.  Clone this repository or download `workflow.json`.
2.  Open your **n8n** instance.
3.  Go to **Workflows** > **Import from File** and select the JSON file.
4.  Configure your **Google Gemini API** credentials in the AI Agent node.
5.  Click **Execute Workflow** to start the agent.

---
*Created by [Ahsaan Ullah](https://github.com/MAhsaanUllah)*