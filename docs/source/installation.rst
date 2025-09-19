Installation
============

.. _installation:

This page provides detailed instructions for installing and setting up **Curaitor Agent**.  
The installation process is divided into two main parts:

1. Installing **Curaitor Agent** and its dependencies.  
2. Setting up the **MCP Inspector Tool** (optional but recommended).  

Prerequisites
-------------

Before you begin, ensure you have the following:

- A Unix-based environment (Linux or macOS recommended).  
- Internet access to download dependencies.  
- Basic familiarity with the command line.  

Installing Curaitor Agent
-------------------------

The project uses `uv <https://astral.sh/uv/>`_, a modern Python package and environment manager.  

1. **Install uv**:

   .. code-block:: bash

      curl -LsSf https://astral.sh/uv/install.sh | sh

2. **Clone the repository**:

   .. code-block:: bash

      git clone <your-repo-url>
      cd curaitor-agent

3. **Initialize the project**:

   .. code-block:: bash

      uv init
      uv add -r requirements.txt

4. **Run the web interface**:

   .. code-block:: bash

      uv run adk web

Dependency Management
---------------------

Curaitor Agent relies on reproducible environments.  
You should keep your dependencies synchronized at all times.

- **Sync when ``requirements.txt`` is updated**:

  .. code-block:: bash

     uv sync

- **Add a new package**:

  .. code-block:: bash

     uv add package-name

  .. note::

     Don’t forget to update ``requirements.txt`` after adding or removing a dependency.

MCP Inspector Tool
------------------

The **Model Context Protocol (MCP) Inspector** is an optional utility that helps verify your MCP server connection and test available tools.  

Requirements
~~~~~~~~~~~~

- `nvm <https://github.com/nvm-sh/nvm>`_ (Node Version Manager)  
- **Node.js ≥ 18** (v22 recommended)  

Setup
~~~~~

1. **Install nvm**:

   .. code-block:: bash

      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | \
      . "$HOME/.nvm/nvm.sh"

2. **Install Node.js v22**:

   .. code-block:: bash

      nvm install 22

3. **Verify versions**:

   .. code-block:: bash

      node -v   # v22.19.0
      npm -v    # 10.9.3

4. **Run the MCP Inspector**:

   .. code-block:: bash

      npx @modelcontextprotocol/inspector uv run tools/mcp_server.py

5. In the MCP Inspector UI, click **Connect → test tools**.

.. important::

   - Always use **Node.js v22.x** when running the MCP Inspector.  
   - Keep your environment synchronized with ``requirements.txt`` to ensure reproducibility.  

Troubleshooting
---------------

- If ``uv`` is not found after installation, make sure ``~/.local/bin`` is in your PATH.  
- When upgrading Node.js versions, run ``nvm use 22`` to ensure compatibility.  
- If dependencies fail to install, try cleaning the environment with:

  .. code-block:: bash

     uv clean
     uv sync

Next Steps
----------

Once installation is complete, you can proceed to:

- :doc:`quickstart` — Run Curaitor Agent with example commands.  
- :doc:`mcp_inspector` — Learn more about using the MCP Inspector.  
- :doc:`usage` — Explore advanced usage patterns.
