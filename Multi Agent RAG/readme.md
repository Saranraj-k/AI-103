# Develop AI Agents in Azure

This repository contains a hands-on workshop for building, extending, evaluating, and deploying AI agents on Microsoft Azure. It is designed for developers and solution architects who want to learn how to create practical agent-based applications using Azure AI Foundry, model deployments, custom tools, knowledge grounding, and orchestration patterns.

The labs in this repo walk through the end-to-end process of building agent experiences, from the initial setup and prompt engineering to MCP integration, multi-agent workflows, and monitoring and safety practices.

> [!IMPORTANT]
> To complete the exercises in this repository, you will need an Azure subscription with permission to provision the required Azure resources and AI services. If you do not already have one, you can create a free Azure account at https://azure.microsoft.com/free.

> [!NOTE]
> These labs are intended to complement the Microsoft Learn learning path for developing AI agents in Azure. You can also access the workshop content in the GitHub Pages site for this repo.

## What you will learn

- How to create and ground an AI agent using Azure AI Foundry
- How to connect remote MCP servers and client applications to agents
- How to add custom function tools to extend agent capabilities
- How to build and orchestrate multi-agent solutions
- How to integrate agents with enterprise knowledge and Microsoft 365 scenarios
- How to observe, evaluate, and secure AI agents in production settings

## Repository overview

The repo is organized into several key areas:

- `Instructions/` – workshop instructions and consolidated lab content
- `Instructions/Consolidated/` – the primary workshop modules and tasks
- `Labfiles/` – starter projects, setup scripts, and solution implementations for each lab
- `tools/` – repository automation and validation scripts
- `index.md`, `workshop.md`, and related site files – static site content for the workshop
- `LICENSE` – repository license terms

## Workshop structure

The repository is grouped into four main learning tracks:

### A. Build and extend AI agents
Topics include creating agents, grounding them with data, using MCP servers, and calling them from client applications.

### B. Integrate agents with enterprise knowledge and Microsoft 365
Topics include AI agent integration with enterprise knowledge systems, Teams, Microsoft 365 Copilot, and workplace intelligence scenarios.

### C. Build multi-agent solutions with Agent Framework
Topics include agent orchestration, tools, routing, and multi-agent collaboration patterns.

### D. Observe, evaluate, and secure agents
Topics include tracing, evaluation, and red-team testing for robust agent operations.

## Prerequisites

Before starting the labs, make sure you have:

- An Azure subscription with access to required Azure AI services and model deployments
- Permission to create and configure Azure resources
- Python 3.13 or later for local code execution when applicable
- A modern code editor such as Visual Studio Code
- Access to the relevant Azure AI and app tooling used in the exercises

## Getting started

1. Clone this repository to your machine.
2. Open the repo in Visual Studio Code.
3. Review the workshop agenda in `workshop.md` or the published GitHub Pages version.
4. Start with the setup tasks for the first lab in `Instructions/Consolidated/`.
5. Follow the lab-specific instructions in the relevant section of the `Instructions` folder.
6. Use the starter code and solution files in `Labfiles/` as needed during the exercises.

## Project layout

```text
.
├── Instructions/
│   ├── Consolidated/
│   └── Exercises/
├── Labfiles/
│   ├── A-build-and-extend-ai-agents/
│   ├── B-integrate-agents-with-enterprise-knowledge-and-m365/
│   ├── C-build-multi-agent-solutions-with-agent-framework/
│   ├── D-observe-evaluate-and-secure-agents/
│   └── 08-agent-orchestration/
├── tools/
├── LICENSE
├── index.md
├── readme.md
├── workshop.md
├── explore.md
├── labs.json
└── _config.yml
```

## Suggested learning path

A typical flow through the workshop is:

1. Complete the setup tasks for the first session
2. Build a basic agent and connect it to tools or data
3. Add grounding and remote integrations
4. Explore orchestration with multiple agents
5. Evaluate tracing, quality, and security implications
6. Extend the solution using the optional labs and enterprise scenarios

## Using the lab files

Each lab folder under `Labfiles/` typically contains:

- `setup/` – environment preparation and bootstrap scripts
- `Python/` – starter and student code
- `Solution/` – reference implementation for completed work
- `infra/` – deployment resources or configuration files for Azure provisioning

Use the setup instructions in each lab before running code locally.

## Reporting issues

If you run into problems while working through the exercises, please open an issue in this repo so the workshop content can be improved and updated.

## License

This project is licensed under the terms found in the `LICENSE` file.

## Additional resources

- Microsoft Learn training path for AI agents in Azure
- GitHub Pages workshop site for the lab content
- Azure AI Foundry documentation and developer resources

---

This repository is intended as a practical, code-first learning experience for building AI agents on Azure. Start with the first lab, follow the setup steps carefully, and progressively extend the agent patterns as you move through the modules.

