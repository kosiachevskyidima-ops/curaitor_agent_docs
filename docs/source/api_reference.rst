API Reference
=============

.. _api_reference:

This document provides a detailed reference for the **Curaitor Agent** API,  
built on the **Google ADK** with **MCP tool integration**.  

It covers modules, classes, functions, and examples for using the agent programmatically.

Overview
--------

The Curaitor Agent provides:

- Integration with **multiple LLM providers** (OpenAI, Google Gemini, OpenRouter).  
- Normalization and mapping of model identifiers across providers.  
- Seamless **MCP toolset integration** for external process orchestration.  
- Compatibility with **Google ADK agents** for flexible workflows.  

Modules
-------

.. toctree::
   :maxdepth: 2

   modules/agent

.. note::

   Each module section contains public classes, functions, and their descriptions.  

Agent Module
------------

.. automodule:: curaitor_agent.agent
   :members:
   :undoc-members:
   :show-inheritance:

.. rubric:: Example Usage

.. code-block:: python

   from curaitor_agent.agent import root_agent

   # Access the MCP-enabled agent
   print(f"Agent: {root_agent.name} | Model: {root_agent.model}")

   # Use it within a workflow
   # (e.g., call methods, interact with MCP tools)

MCP Tool Integration
--------------------

Two MCP toolsets are configured for this agent:

- ``mcp_toolset`` – General-purpose tool connection.  
- ``data_initializer_mcp`` – Dataset initialization toolset.  

They use:

- :class:`mcp.StdioServerParameters` – for MCP subprocess configuration.  
- :class:`StdioConnectionParams` – for connection management.  

These toolsets allow the agent to interact with external processes,  
such as custom servers, dataset processors, or specialized tools.  

Best Practices
--------------

- Ensure the correct API key is set for the configured provider:  
  ``OPENAI_API_KEY``, ``GOOGLE_API_KEY``, or ``OPENROUTER_API_KEY``.  
- Use ``_normalize_model_for_provider`` to align model names with provider requirements.  
- Handle exceptions for provider errors and MCP initialization timeouts.  
- Validate ``config.yaml`` before running the agent to ensure correct setup.  

Next Steps
----------

- Extend the agent with **custom MCP tools**.  
- Integrate into larger **ADK-based pipelines**.  
- Use multiple MCP servers for distributed workflows.  
- Explore hybrid LLM setups (e.g., OpenRouter + Gemini fallback).  
