<h1 align="center">OmniFlow AI</h1>
<p align="center"><b>Autonomous Multi-Agent Orchestration & Enterprise Automation Engine</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/OmniFlow_AI-Autonomous_Orchestrator-blueviolet?style=for-the-badge&logo=ai" alt="OmniFlow AI">
</p>

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

## 📑 Project Overview

**OmniFlow AI** is a professional-grade, autonomous multi-agent system designed for enterprise-level automation. Engineered using the **n8n** framework, it implements a highly-scalable "OpenClaw" orchestration pattern that consolidates fragmented business tools into a single, intelligent interface.

The system acts as an **Autonomous Executive**, interpretating multi-modal inputs (Voice, Text, Vision) and executing complex, cross-platform workflows. By sitting at the intersection of LLM reasoning and professional toolsets, OmniFlow AI automates the "thinking" as well as the "doing," making it a powerful asset for modern AI-driven operations.

---

## 🏗️ Technical Architecture

```mermaid
graph TD
    %% Global B&W Styling
    classDef mainNode fill:#000,stroke:#fff,stroke-width:2px,color:#fff
    classDef subNode fill:#fff,stroke:#000,stroke-width:1px,color:#000
    classDef container fill:#f5f5f5,stroke:#000,stroke-dasharray: 5 5

    %% Entry Points
    User((User)) -- "Multi-modal Input" --> Gateway[Telegram Gateway]
    
    subgraph "Preprocessing & Security"
        Gateway --> Auth{Security Check}
        Auth -- Authorized --> Logic[Input Normalization]
        Logic --> Transcribe[Whisper Voice Transcription]
        Logic --> Vision[GPT-4o Vision OCR]
    end

    %% Core Orchestration
    subgraph "Agentic Core"
        Transcribe --> Orchestrator[OmniFlow Orchestrator Agent]
        Vision --> Orchestrator
        Orchestrator <--> Memory[(PostgreSQL Persistent History)]
    end

    %% Specialized Toolsets
    subgraph "Execution Layer"
        Orchestrator --> GSuite[G-Suite Pipeline - Gmail Drive Sheets]
        Orchestrator --> Intelligence[Research Pipeline - Perplexity ScrapeGraph]
        Orchestrator --> Knowledge[Knowledge Pipeline - Qdrant RAG]
        Orchestrator --> Creative[Media Pipeline - Grok Image Video]
    end

    %% Feedback Loop
    GSuite --> Orchestrator
    Intelligence --> Orchestrator
    Knowledge --> Orchestrator
    Creative --> Orchestrator

    %% Output
    Orchestrator --> Response[Final Synthesis]
    Response --> User

    %% Apply Styles
    class Gateway,Orchestrator,Response mainNode
    class Auth,Logic,Transcribe,Vision,GSuite,Intelligence,Knowledge,Creative subNode
```

---

## ⚙️ Core Pipelines

The OmniFlow AI architecture is built around several "High-Throughput Pipelines" that handle specific enterprise tasks:

### 1. **G-Suite Workflow Pipeline**
*   **Purpose**: Complete automation of the Google Workspace ecosystem.
*   **Mechanism**: Uses **Model Context Protocol (MCP)** to bridge n8n with G-Suite APIs.
*   **Capabilities**: Automated draft generation, intelligent calendar conflict resolution, and dynamic documentation synthesis.

### 2. **Cognitive Research Pipeline**
*   **Purpose**: Real-time information gathering and data extraction.
*   **Mechanism**: Chained execution between **Perplexity AI** (for broad search) and **ScrapeGraph AI** (for structured scraping).
*   **Capabilities**: Competitor analysis reports, market trend extraction, and cited source consolidation.

### 3. **RAG & Knowledge Pipeline**
*   **Purpose**: Context-aware retrieval of private enterprise data.
*   **Mechanism**: High-speed vector search via **Qdrant** with **Cohere Reranking** for maximum relevance.
*   **Capabilities**: Private policy querying, internal document search, and personal knowledge base interaction.

### 4. **Multi-modal Input Pipeline**
*   **Purpose**: Seamless handling of diverse communication types.
*   **Mechanism**: Parallel processing of **Whisper** (Audio) and **GPT-4o/Gemini** (Vision/Text).
*   **Capabilities**: Hands-free voice operation, visual document analysis, and complex OCR-based triggers.

---

## 🛠️ Technology Stack

| Stack | Technologies |
| :--- | :--- |
| **Frameworks** | n8n, LangChain |
| **Intelligence** | GPT-4o, Gemini 1.5 Pro, Whisper, Cohere |
| **Databases** | PostgreSQL (History), Qdrant (Vector) |
| **Integrations** | Gmail, Google Drive, Calendar, Google Sheets (Excel), Google Docs, Google Slides |
| **Research** | Perplexity AI, ScrapeGraph AI |
| **Media** | Grok (xAI) |

---

## 💼 Deployment & Configuration

1.  **Workflow Import**: Import the production-ready `OmniFlow_AI.json` into n8n.
2.  **Auth Configuration**: Set your authorized `USER_ID` and Telegram credentials.
3.  **MCP Server Setup**: Connect your MCP servers for Google Workspace endpoints.
4.  **Credential Management**: Securely store API keys for OpenAI, Google, and Perplexity within n8n.

---

## 📄 License
This system is provided under the **MIT License**. It is designed as a template for professional-grade autonomous agent deployments.

---
<p align="center">
  <b>Developed for Professional Portfolio Use | n8n Multi-Agent System v1.0</b>
</p>
