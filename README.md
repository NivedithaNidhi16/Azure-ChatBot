
## 📌 Project Title

**Azure  Chatbot using MCP Server**

(You can tweak this to: *Azure Resource & Cost Optimization AI Chatbot (MCP-based)*)

---

## 📖 Overview

This project is a **Proof of Concept (POC)** for an **AI-powered Azure chatbot** built using the **Model Context Protocol (MCP)**.
The chatbot interacts with Azure resources using **custom MCP tools** to help users:

* View Azure resource groups
* Analyze cost-related information
* Identify idle or unnecessary resources
* Suggest resources that can potentially be deleted for cost optimization

The goal of this project is to demonstrate how **LLMs + MCP servers** can be used to build **agentic cloud assistants** for real-world DevOps and FinOps use cases.

---

## 🧠 Why This Project?

Managing cloud costs manually requires navigating multiple Azure dashboards and services.
This POC explores how an **AI agent** can act as a **conversational interface** on top of Azure APIs to:

* Reduce operational overhead
* Improve visibility into cloud usage
* Assist engineers in cost optimization decisions

---

## 🏗️ Architecture Overview

High-level flow:

```
User Query
   ↓
LLM (Chat Interface)
   ↓
MCP Client
   ↓
Custom MCP Server
   ↓
Azure SDK / Azure APIs
   ↓
Azure Subscription Data
```

### Key Components

* **LLM** – Interprets user queries and decides which tool to invoke
* **MCP Server** – Acts as a bridge between the LLM and Azure
* **Azure MCP Tools** – Custom tools that fetch and analyze Azure data
* **Azure SDK / APIs** – Used to retrieve resource and cost information

---

## 🔌 MCP Server Implementation

The MCP server is implemented as a **custom Node.js MCP server** that:

* Registers Azure-related tools
* Exposes them via the MCP protocol
* Executes Azure SDK calls securely using Azure credentials

Each tool is designed with:

* Clear input schemas
* Structured outputs
* Safe, read-only access (POC scope)

---

## 🧰 Tools Implemented

Currently, the following MCP tools are implemented:

### 1️⃣ Get Azure Resource Groups

* Fetches all resource groups under the configured subscription
* Helps users understand what resources exist in their environment

### 2️⃣ Cost Analysis Tool

* Retrieves cost-related data for resources
* Provides a high-level view of spending trends

### 3️⃣ Resource Cleanup Suggestions

* Identifies potentially unused or idle resources
* Suggests candidates for deletion to optimize costs

> ⚠️ **Note:** This tool provides recommendations only and does not delete resources automatically.

---

## 💬 Example Queries

Users can interact with the chatbot using natural language, such as:

* “List all resource groups in my Azure subscription”
* “Which resources are contributing most to the cost?”
* “Are there any unused resources I can delete?”
* “Give me cost optimization suggestions”

---

## 🔐 Authentication & Security

* Uses **Azure Identity (DefaultAzureCredential)**
* No hardcoded secrets
* Follows Azure best practices for authentication

---

## 🚀 How to Run (High Level)

```bash
# Install dependencies
npm install

# Start MCP Server
node server.js

# Connect MCP server to the LLM client
```

> Detailed setup steps can be added if needed, but for a POC this level is usually enough.

---

## 📈 Future Enhancements

Planned improvements for future iterations:

* Add more Azure tools (VM status, storage analysis, networking)
* Fine-grained cost breakdown per service
* Role-based access control for users
* Auto-remediation workflows (with approvals)
* Integration with dashboards or ticketing systems

---

## 🧪 Status

* ✅ Proof of Concept
* 🚧 Actively extensible
* 🎯 Focused on learning MCP + Agentic AI patterns

---



