# MCP Integration Lab

This project demonstrates how to use Model Context Protocol (MCP) tools with Azure AI Agents in two common patterns:

- connecting an agent to a remote MCP server (Microsoft Learn Docs)
- creating a local custom MCP server with tool functions and exposing them to an agent

The sample code is located in the Python folder and is designed for the Microsoft Learn lab: "Extend agents with Model Context Protocol (MCP) tools."

## Project structure

- `Python/agent.py` - connects to a remote MCP server and creates an Azure AI agent that can approve and use MCP requests
- `Python/server.py` - a local FastMCP server that exposes inventory and sales tools
- `Python/client.py` - a local MCP client that starts the server, discovers tools, and connects them to an Azure AI agent
- `Python/requirements.txt` - Python dependencies for the lab

## What the lab demonstrates

### 1. Remote MCP server integration

`agent.py` uses the `MCPTool` class to connect an Azure AI agent to the Microsoft Learn Docs MCP server at:

`https://learn.microsoft.com/api/mcp`

This allows the agent to fetch technical documentation and answer questions using trusted source content.

### 2. Custom local MCP server

`server.py` defines a `FastMCP` server named `Inventory` and exposes tools such as:

- `get_inventory_levels()`
- `get_weekly_sales()`

These tools simulate a retail backend and provide data the agent can use to make recommendations.

### 3. Tool execution via MCP client

`client.py` starts the local MCP server, connects to it over stdio, lists the available tools, and creates a function wrapper for each tool. The agent then uses those tools to respond to user prompts like inventory checks and restocking recommendations.

## Prerequisites

Before running the project, make sure you have:

- Python 3.12 or newer
- Azure subscription access
- An Azure AI Foundry project and deployed model
- Azure CLI installed and signed in (`az login`)
- Access to the Azure identity credential flow used by `DefaultAzureCredential`

## Setup

From the `Python` folder, create and activate a virtual environment:

```bash
python -m venv labenv
```

On Windows PowerShell:

```powershell
.\labenv\Scripts\Activate.ps1
```

Then install dependencies:

```bash
pip install -r requirements.txt
```

Create a `.env` file in the `Python` folder with values similar to:

```env
PROJECT_ENDPOINT="https://<your-project-endpoint>.services.ai.azure.com/api/projects/<your-project-name>"
MODEL_DEPLOYMENT_NAME="gpt-5"
```

You can copy these values from your Azure AI Foundry project and model deployment.

## Run the remote MCP example

From the `Python` folder:

```bash
python agent.py
```

This creates an Azure AI agent that connects to the Microsoft Learn MCP server and answers documentation questions.

## Run the local custom MCP example

From the `Python` folder:

```bash
python client.py
```

When prompted, try messages such as:

```text
Show me the current inventory levels for all products.
```

The agent will call the MCP server tools, retrieve the inventory and sales data, and generate a recommendation based on the instructions you configured.

## Notes

- The local client starts the server in-process over stdio transport for the lab.
- The remote MCP example may trigger approval requests before tool execution; those are automatically approved in the sample code.
- If model rate limits or quota issues occur, wait a bit and retry the request.

## Typical workflow

1. Create or select an Azure AI Foundry project.
2. Deploy a model such as `gpt-5`.
3. Configure your `.env` values.
4. Run the remote MCP sample or the custom inventory MCP sample.
5. Observe how the model discovers and calls MCP tools to fulfill user requests.

## References

- Microsoft Learn: Model Context Protocol (MCP)
- Azure AI Foundry Agent service documentation
- Azure AI Projects Python SDK
