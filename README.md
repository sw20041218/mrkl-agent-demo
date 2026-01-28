by **Wen Sun**

A lightweight agent-based demo built with LangChain and Streamlit, showcasing how a MRKL (Modular Reasoning, Knowledge and Language) agent performs multi-step reasoning and tool selection to answer complex questions.

This project focuses on agentic reasoning rather than full-stack engineering, and is designed to be reproducible and stable for coursework demonstration.

---

## 🚀 Key Features
+ **Agentic Reasoning (MRKL)**  
Uses a MRKL-style agent to decompose complex questions into reasoning steps and select appropriate tools.
+ **Tool Selection & Orchestration**  
Integrates multiple tools, including web search, calculator, and SQL database querying.
+ **Deterministic Playback Mode**  
Uses prerecorded agent execution traces (`.pickle` files) to demonstrate reasoning behavior without relying on live API calls.
+ **Interactive Web UI**  
Built with Streamlit for a simple, local, browser-based interface.

---

## 🛠 Tech Stack
+ **Language:** Python 3.11  
+ **Agent Framework:** LangChain  
+ **Frontend:** Streamlit  
+ **Database:** SQLite (Chinook sample database)  
+ **Dependency Management:** Poetry

---

## ⚙️ How to Install & Run
### Clone the Repository
```bash
git clone https://github.com/sw20041218/mrkl-agent-demo.git
cd streamlit-agent
```

## ⚙️ How to Install & Run
### Create Virtual Environment
```plain
python -m venv .venv
```

### Activate the Environment
Windows (PowerShell)

```plain
.\.venv\Scripts\Activate.ps1
```

macOS / Linux

```plain
source .venv/bin/activate
```

### Install Dependencies
```plain
poetry install
```

### Run the App
```plain
python -m streamlit run streamlit_agent/mrkl_demo.py 
```

Open your browser at:

```plain
http://localhost:8501
```

---

## 📝 Notes
+ The example questions are designed to resemble natural student-style queries.
+ Prerecorded `.pickle` files are used to replay agent reasoning steps for stability and reproducibility.
+ This approach avoids API quota and billing issues while still demonstrating agent behavior.
## Video of running
https://github.com/sw20041218/mrkl-agent-demo/assets/USER_ID/VIDEO_ID



