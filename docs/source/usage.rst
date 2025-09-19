Usage Guide
===========

.. _usage:

This guide provides detailed instructions on how to run and interact with **Curaitor Agent** after installation.
It covers launching the web interface, using the MCP Inspector, managing scientific data workflows, and troubleshooting common issues.

Running the Web Interface
-------------------------

The Curaitor Agent includes a lightweight web application that allows you to manage tasks, upload datasets, and interact with tools through a browser-based interface.

Steps
^^^^^

1. **Open a terminal and navigate to your project directory**:

   .. code-block:: bash

      cd curaitor-agent

   .. note::
      Ensure you are in the root directory of your Curaitor Agent project where ``uv`` commands are available.

2. **Start the web interface**:

   .. code-block:: bash

      uv run adk web

   - This command launches the web server locally.
   - By default, the server runs on port ``8000``.

3. **Open the web interface in your browser**:

   .. code-block:: text

      http://localhost:8000

   - You should see the Curaitor Agent dashboard.
   - Here, you can upload datasets, manage tasks, and use available tools.

4. **Using a custom port**:

   .. code-block:: bash

      uv run adk web --port 8080

---

Using the MCP Inspector
-----------------------

The **MCP Inspector** is a tool for testing and verifying connections between Curaitor Agent and its integrated tools.

Steps
^^^^^

1. **Ensure the Curaitor Agent server is running**.

2. **Launch the MCP Inspector**:

   .. code-block:: bash

      npx @modelcontextprotocol/inspector uv run tools/mcp_server.py

3. **Connect through the MCP Inspector UI**:

   - Click **Connect** to establish a connection with the running server.
   - Select **Test Tools** to check available commands and ensure they respond correctly.

.. important::
   Use **Node.js v22.x** for compatibility. Running MCP Inspector with an unsupported Node version may lead to connection failures.

---

Example Workflow
----------------

Here is a step-by-step example workflow to help you get started:

1. **Start the Curaitor Agent**:

   .. code-block:: bash

      uv run adk web

2. **Verify server tools with MCP Inspector**:

   .. code-block:: bash

      npx @modelcontextprotocol/inspector uv run tools/mcp_server.py

3. **Upload and process data**:

   - Use the web interface to upload your dataset.
   - Apply tools such as parsing, filtering, or data transformations.
   - Review results and export them for downstream analysis.

---

Best Practices
--------------

- **Keep dependencies up-to-date**:

  .. code-block:: bash

     uv sync

- **Use version control** (e.g., Git) to track changes in project setups and workflows.
- **Test new tools** in MCP Inspector before integrating them into production workflows.
- **Ensure reproducibility**: Run experiments in a clean environment to avoid inconsistencies.

---

Troubleshooting
---------------

- **Web interface fails to start**:
  - Ensure all dependencies are installed.
  - Run ``uv sync`` to synchronize packages.

- **MCP Inspector cannot connect**:
  - Verify that the Curaitor Agent server is running.
  - Check firewall settings or network rules that may block connections.

- **Package issues**:
  If a tool or package fails, remove and re-add it:

  .. code-block:: bash

     uv remove package-name
     uv add package-name

---

Next Steps
----------

Once you are comfortable using Curaitor Agent:

- Explore the **API reference** for programmatic integration.
- See the **MCP Inspector** documentation for advanced testing.
- Extend workflows for your research by combining multiple tools and datasets.
- Contribute to the project by following the guidelines in the :doc:`contribution` page.
- Stay updated with the latest features and improvements by checking the repository regularly.
- For licensing details, refer to the :doc:`license` page.
- Always ensure your environment is synchronized with ``requirements.txt`` for consistent results.