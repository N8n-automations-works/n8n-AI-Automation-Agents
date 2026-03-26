<p align="center">
  <img src="https://img.shields.io/badge/OmniFlow_AI-Autonomous_Orchestrator-blueviolet?style=for-the-badge&logo=ai" alt="OmniFlow AI">
</p>

<p align="center">
  <b>The Ultimate Autonomous Multi-Agent System for Enterprise Automation</b>
</p>

---

<p align="center">
  <img src="https://img.shields.io/badge/n8n-Workflow_Automation-FF6C37?style=flat-square&logo=n8n&logoColor=white" alt="n8n">
  <img src="https://img.shields.io/badge/LangChain-AI_Framework-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangChain">
  <img src="https://img.shields.io/badge/OpenAI-GPT--4o_/_Whisper-412991?style=flat-square&logo=openai&logoColor=white" alt="OpenAI">
  <img src="https://img.shields.io/badge/Google_Gemini-Reasoning_Engine-4285F4?style=flat-square&logo=googlegemini&logoColor=white" alt="Google Gemini">
  <img src="https://img.shields.io/badge/Perplexity_AI-Web_Intelligence-00A294?style=flat-square&logo=perplexity&logoColor=white" alt="Perplexity AI">
  <img src="https://img.shields.io/badge/Qdrant-Vector_Database-FF4136?style=flat-square&logo=qdrant&logoColor=white" alt="Qdrant">
  <img src="https://img.shields.io/badge/PostgreSQL-Chat_Memory-336791?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Gmail-Email_Automation-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Gmail">
  <img src="https://img.shields.io/badge/Google_Drive-Cloud_Storage-4285F4?style=flat-square&logo=googledrive&logoColor=white" alt="Google Drive">
  <img src="https://img.shields.io/badge/Google_Calendar-Scheduling-4285F4?style=flat-square&logo=googlecalendar&logoColor=white" alt="Google Calendar">
  <img src="https://img.shields.io/badge/Google_Sheets-Data_Management-34A853?style=flat-square&logo=googlesheets&logoColor=white" alt="Google Sheets">
  <img src="https://img.shields.io/badge/Google_Docs-Documentation-4285F4?style=flat-square&logo=googledocs&logoColor=white" alt="Google Docs">
  <img src="https://img.shields.io/badge/Google_Slides-Presentations-FBBC04?style=flat-square&logo=googleslides&logoColor=white" alt="Google Slides">
</p>

---

## 📖 Executive Summary

**OmniFlow AI** is a professional-grade, autonomous multi-agent orchestration system built on the **n8n** automation framework. Designed as a functional "OpenClaw" simulation, it transforms a standard Telegram interface into a powerful AI command center. 

Unlike traditional chatbots, OmniFlow AI is an **autonomous executive**. It understands complex, multi-modal inputs (Text, Voice, Image) and intelligently delegates tasks to a fleet of specialized sub-agents. Whether it's performing deep market research via Perplexity, managing your entire G-Suite workspace via MCP (Model Context Protocol), or maintaining a long-term memory via Qdrant/Postgres, OmniFlow AI operates with a "Think-Plan-Execute" mindset.

---

## 🏗️ Technical Architecture

The system utilizes a hierarchical agentic design where a central **Orchestrator** manages state, memory, and tool invocation.

```mermaid
graph TD
    %% Global Styling
    classDef primary fill:#6c5ce7,stroke:#333,stroke-width:2px,color:#fff
    classDef secondary fill:#00cec9,stroke:#333,stroke-width:1px
    classDef storage fill:#ff7675,stroke:#333,stroke-width:1px
    classDef tool fill:#55efc4,stroke:#333,stroke-width:1px

    %% Entry Points
    User((User)) -- "Voice / Text / Image" --> TG[Telegram Gateway]
    
    subgraph "Preprocessing & Security"
        TG --> Auth{ID Verification}
        Auth -- "Authorized" --> Transcribe[Whisper Transcription]
        Auth -- "Authorized" --> Vision[GPT-4o Vision / OCR]
        Transcribe --> Normalized[Input Normalization]
        Vision --> Normalized
    end

    %% Core Intelligence
    subgraph "Core Agentic Engine"
        Normalized --> Orchestrator["🧠 OmniFlow Orchestrator<br/>(LangChain Agent)"]
        Orchestrator <--> Memory[(PostgreSQL Persistent History)]
    end

    %% Specialized Toolsets
    subgraph "Agentic Toolsets (The G-Suite & Beyond)"
        Orchestrator --> Web["🌐 <b>Intelligence Suite</b><br/>Perplexity (RAG)<br/>ScrapeGraph AI"]
        Orchestrator --> GSuite["💼 <b>Google Workspace (MCP)</b><br/>Gmail, Drive, Calendar<br/>Sheets (Excel), Docs, Slides"]
        Orchestrator --> Knowledge["📂 <b>Knowledge Base</b><br/>Qdrant Vector DB<br/>Cohere Reranker"]
        Orchestrator --> Media["🎨 <b>Media Generation</b><br/>Grok Image/Video Gen<br/>Workflow Sub-Agents"]
    end

    %% Feedback Loop
    Web --> Orchestrator
    GSuite --> Orchestrator
    Knowledge --> Orchestrator
    Media --> Orchestrator

    %% Final Output
    Orchestrator --> Dispatcher{Output Dispatcher}
    Dispatcher -- "Actionable Response" --> ResponseTG[Telegram Final Delivery]

    class Orchestrator primary
    class Memory,Knowledge storage
    class Web,GSuite,Media tool
    class User secondary
```

---

## 🚀 Professional Capabilities

### 🧠 Autonomous Orchestration (OpenClaw Logic)
The agent doesn't just respond; it **reasons**. Using a multi-step planning phase, it breaks down complex requests (e.g., *"Summarize my last 5 emails and create a Google Doc report with a table and a matching presentation slide"*) into a sequence of tool calls.

### 💼 Enterprise Workspace Integration
- **Google Workspace (G-Suite)**: Deep integration via MCP. Handles complex Excel/Sheets manipulations, Gmail drafting/sending, and automatic Calendar management.
- **RAG (Retrieval-Augmented Generation)**: Uses **Qdrant** and **Cohere** to fetch and rank private information from your documents, ensuring responses are grounded in your specific data.

### 🎙️ Multi-modal Mastery
- **Voice Intelligence**: High-fidelity transcription via **OpenAI Whisper**, enabling hands-free automation.
- **Computer Vision**: Uses **GPT-4o Vision** to analyze photos or screenshots sent via Telegram, triggering workflows based on visual context.

### 🌐 Real-time Web Intelligence
- **Advanced Scraping**: Uses **ScrapeGraph AI** to extract data from modern, JavaScript-heavy websites.
- **Live Research**: Powered by **Perplexity AI** for up-to-the-minute information withdrawal with source citations.

---

## 🛠️ Tech Stack & Tooling

| Category | Technology |
| :--- | :--- |
| **Orchestration** | n8n, LangChain |
| **Logic Engines** | Google Gemini 1.5 Pro, OpenAI GPT-4o |
| **Web Research** | Perplexity AI, ScrapeGraph AI |
| **Vector DB** | Qdrant |
| **Persistence** | PostgreSQL |
| **G-Suite** | Gmail, Google Drive, Calendar, Sheets, Docs, Slides |
| **Media Gen** | Grok (xAI) |

---

## 📥 Deployment Guide

1.  **Repository Setup**: Clone this repository and ensure `OmniFlow_AI.json` is accessible.
2.  **n8n Import**: Create a new workflow in your n8n instance and import the `.json` file.
3.  **Environment Variables**:
    *   Set `TELEGRAM_BOT_TOKEN` and your authorized `USER_ID`.
    *   Configure `GOOGLE_OAUTH` for Workspace access.
    *   Input API keys for OpenAI, Gemini, Perplexity, and Qdrant in the credential manager.
4.  **Active Triggers**: Enable the **Telegram Trigger** and **Schedule Trigger** for autonomous background tasks.

---

## 🛡️ License & Acknowledgments
This project is licensed under the MIT License. Developed as a professional-grade demonstration of autonomous multi-agent systems.

---
<p align="center">
  Generated with ❤️ by <b>Antigravity</b> for <b>Vinodhan</b>'s Professional Portfolio
</p>
