Quickstart
==========

.. _quickstart:

Quick Start
-----------

To get started with Curaitor Agent, follow these steps:

.. code-block:: bash

   # Install uv
   curl -LsSf https://astral.sh/uv/install.sh | sh

   # Clone repo
   git clone <your-repo-url>
   cd curaitor-agent

   # Initialize project
   uv init
   uv add -r requirements.txt

   # Run web interface
   uv run adk web

Dependency Management
---------------------

Keep your environment consistent and reproducible with these commands:

- Sync when ``requirements.txt`` is updated:

  .. code-block:: bash

     uv sync

- Add a new package:

  .. code-block:: bash

     uv add package-name

  .. note::

     Don’t forget to update ``requirements.txt`` after adding a new dependency!

MCP Inspector Tool
------------------

The **MCP Inspector** helps verify your MCP server connection and test available tools.

Requirements
~~~~~~~~~~~~

- `nvm <https://github.com/nvm-sh/nvm>`_ (Node Version Manager)  
- **Node.js ≥ 18** (v22 recommended)

Setup
~~~~~

1. Install **nvm**:

   .. code-block:: bash

      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | \
      . "$HOME/.nvm/nvm.sh"

2. Install **Node.js v22**:

   .. code-block:: bash

      nvm install 22

3. Verify versions:

   .. code-block:: bash

      node -v   # v22.19.0
      npm -v    # 10.9.3

4. Run the MCP Inspector:

   .. code-block:: bash

      npx @modelcontextprotocol/inspector uv run tools/mcp_server.py

5. In the MCP Inspector UI, click **Connect → test tools**.

.. important::

   - Ensure you’re using **Node.js v22.x** when running the inspector.  
   - Always keep your environment in sync with ``requirements.txt`` for reproducibility.

License
-------

This project is licensed under the **MIT License**.
