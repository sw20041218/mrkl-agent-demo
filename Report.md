## 🐣 MRKL Agent Demo — Project Report
**Student:** Wen Sun  
**Project Type:** Exploratory AI Tool Usage  
**Submission Format:** Markdown (editable)

## 1. Project Motivation
The goal of this project is **not** to build a large-scale or production-ready system.  
Instead, it is an **exploratory project** focused on understanding how _agentic AI tools_ actually work in practice.

In particular, I wanted to move beyond simply calling an AI API and instead explore:

+ How an AI agent reasons step by step
+ How it decides _which tool to use_
+ What kinds of problems this approach is suitable for
+ Where its limitations become visible

I therefore approached this project from the role emphasized in class:  
**the discoverer**, rather than a user following a fixed tutorial.

## 2. Project Overview
This project implements a **MRKL-style (Modular Reasoning, Knowledge and Language) agent** using the LangChain framework, with a lightweight Streamlit interface for interaction.

The agent is capable of:

+ Receiving a natural language question
+ Breaking the question into reasoning steps
+ Selecting appropriate tools dynamically
+ Combining intermediate observations into a final answer

The emphasis of the project is **the agent’s reasoning and tool orchestration**, not the sophistication of the user interface or dataset.

## 3. Why a MRKL-Style Agent?
### 3.1 Motivation for Choosing MRKL
I chose a MRKL-style agent because it makes the internal behavior of an agent **observable**.

Unlike a single black-box LLM call, a MRKL agent:

+ Explicitly chooses tools such as search, calculator, or database
+ Executes actions step by step
+ Produces intermediate reasoning traces

This transparency makes it possible to understand _what the agent is actually doing_, which aligns closely with the course goal of learning AI tools rather than just using them.

### 3.2 Tools Used in the Agent
The agent integrates three main tools:

+ **Web Search Tool**  
Used for answering questions about current or external information.
+ **Math Tool**  
Used when numerical computation is required.
+ **SQL Database Tool (FooBar DB)**  
Used to query a local SQLite database (Chinook sample database).

The agent decides which tool to invoke based on the question context, rather than following a fixed execution order.

## 4. System Design and Implementation
### 4.1 Agent Architecture
The system consists of:

+ A **single MRKL agent** created using LangChain’s ReAct-style prompt
+ A **tool registry** that the agent can access
+ A **Streamlit-based UI** for local interaction

The agent logic is intentionally kept simple to maintain focus on reasoning behavior rather than system complexity.

### 4.2 Deterministic Playback for Reproducibility
One important design decision was the use of **pre-recorded agent execution traces** (`.pickle` files).

Instead of always calling live APIs, the system can replay saved reasoning sessions for predefined questions.

This choice was made to:

+ Avoid API quota and billing issues
+ Ensure stable and reproducible demonstrations
+ Allow the reasoning process to be observed consistently

This represents a trade-off between real-time flexibility and experimental clarity.

### 4.3 UI Interaction and State Management
While working with Streamlit, I encountered a practical issue:  
previous outputs remained visible in a “grayed-out” state during reruns, which made the interaction confusing.

To address this, I implemented a small **session-state based clearing mechanism** that:

+ Detects when a new submission occurs
+ Clears previous outputs cleanly
+ Improves the clarity of repeated demonstrations

Although this is a small technical detail, it reflects an important lesson:  
**agent demos are not only about reasoning, but also about making behavior understandable to humans.**

## 5. What I Learned from This Project
### 5.1 Strengths of Agent-Based Approaches
Through experimentation, I observed that agent-based systems are particularly useful when:

+ Tasks require multiple types of tools
+ Execution order cannot be fully predetermined
+ Reasoning needs to adapt dynamically to intermediate results

Compared to a single API call, the agent approach provides more flexibility and transparency.

### 5.2 Limitations Observed
This project also made several limitations clear:

+ Reasoning quality is highly sensitive to prompt design
+ Tool selection is not always optimal
+ The agent has no long-term memory or collaboration ability

These limitations helped me better understand **where agentic solutions are appropriate, and where they are not**.

## 6. Relation to Antigravity and Future Work
Although this project does not directly use Antigravity, it aligns with the **agent-first philosophy** discussed in class.

This project can serve as a foundation for:

+ Migrating the agent workflow into an Antigravity environment
+ Experimenting with multi-agent coordination
+ Managing more complex tool interactions

These extensions correspond to topics planned for later stages of the course.

## 7. Conclusion
This project is intentionally small in scale but deliberate in scope.

Rather than optimizing for visual polish or system size, it focuses on:

+ Understanding how an AI agent reasons
+ Observing how tools are orchestrated
+ Reflecting on the strengths and limitations of agentic AI tools

The project demonstrates not only that an AI agent can be built, but that I understand **why and how it behaves the way it does**, which is the central objective of this course.

