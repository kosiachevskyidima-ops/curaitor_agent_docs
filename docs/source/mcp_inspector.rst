MCP Inspector
=============

.. _mcp_inspector:

The **Model Context Protocol (MCP) Inspector** is a companion tool designed to verify your MCP server connection and test available tools.  
It is especially useful for developers and researchers who want to confirm that Curaitor Agent’s integration with MCP is working correctly.

Overview
--------

The MCP Inspector provides a lightweight interface to:

- Check whether your MCP server is running properly.  
- Interactively test tool availability and connectivity.  
- Debug issues related to server–client communication.  

This tool is optional, but it is strongly recommended if you plan to extend Curaitor Agent with additional tools or servers.

Requirements
------------

Before setting up the MCP Inspector, ensure that you have the following:

- `nvm <https://github.com/nvm-sh/nvm>`_ (Node Version Manager).  
- **Node.js ≥ 18** (with **v22 recommended** for stability and compatibility).  
- A properly installed and configured Curaitor Agent environment (see :doc:`installation`).  

Installation and Setup
----------------------

1. **Install nvm**:

   .. code-block:: bash

      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | \
      . "$HOME/.nvm/nvm.sh"

   .. note::

      After installing, restart your terminal or run ``source ~/.bashrc`` (or ``.zshrc``)  
      to activate nvm.

2. **Install Node.js v22**:

   .. code-block:: bash

      nvm install 22
      nvm use 22

3. **Verify installation**:

   .. code-block:: bash

      node -v   # should print v22.x.x
      npm -v    # should print npm 10.x.x

4. **Run the MCP Inspector**:

   .. code-block:: bash

      npx @modelcontextprotocol/inspector uv run tools/mcp_server.py

   This launches the inspector and attempts to connect to your MCP server.

Usage
-----

- When the MCP Inspector UI opens:  
  1. Click **Connect**.  
  2. Select **test tools** to view and validate available functionality.  
  3. Confirm that the server responds with the expected output.

.. important::

   - Always use **Node.js v22.x** for running the MCP Inspector.  
   - Ensure the Curaitor Agent server is running before connecting.  
   - If you encounter issues, verify that your environment is synced with ``requirements.txt`` (run ``uv sync``).

Troubleshooting
---------------

- **Inspector does not start**:  
  Make sure ``npx`` is installed and that you are running Node.js v22.  

- **Server connection fails**:  
  Ensure ``uv run tools/mcp_server.py`` is working without errors.  

- **Old Node.js version in use**:  
  Run ``nvm use 22`` to explicitly activate Node.js 22 in your shell session.  

Next Steps
----------

Once the MCP Inspector confirms that your server is functioning correctly, you can:

- Explore advanced usage in the :doc:`usage` guide.  
- Integrate additional tools for custom workflows.  
- Return to the :doc:`quickstart` guide for a full workflow overview.  
