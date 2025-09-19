API Reference
=============

.. _api_reference:

This document provides a detailed reference for the **Curaitor Agent** API.  
It includes available modules, classes, functions, and usage examples for programmatic integration.

Overview
--------

The Curaitor Agent API allows programmatic interaction with the web interface, tools, and data workflows.  
You can use it to automate tasks, integrate custom tools, and manage datasets efficiently.

Modules
-------

.. toctree::
   :maxdepth: 2

   modules/agent
   modules/tools
   modules/data_processing

.. note::
   Each module section below contains the public classes, functions, and their descriptions.

Agent Module
------------

.. automodule:: curaitor_agent.agent
   :members:
   :undoc-members:
   :show-inheritance:

.. rubric:: Example Usage

.. code-block:: python

   from curaitor_agent.agent import CuraitorAgent

   agent = CuraitorAgent()
   agent.start_web_interface(port=8000)
   agent.upload_dataset("data/sample.csv")
   results = agent.process_data(tool="parser")
   print(results)

Tools Module
------------

.. automodule:: curaitor_agent.tools
   :members:
   :undoc-members:
   :show-inheritance:

.. rubric:: Example Usage

.. code-block:: python

   from curaitor_agent.tools import DataParser, DataFilter

   parser = DataParser()
   filtered_data = DataFilter().apply(parser.parse("data/sample.csv"))
   print(filtered_data)

Data Processing Module
----------------------

.. automodule:: curaitor_agent.data_processing
   :members:
   :undoc-members:
   :show-inheritance:

.. rubric:: Example Usage

.. code-block:: python

   from curaitor_agent.data_processing import Transformer

   transformer = Transformer()
   transformed = transformer.apply_transformation("data/sample.csv", method="normalize")
   print(transformed)

Best Practices
--------------

- Always handle exceptions when calling API methods to prevent runtime errors.
- Verify that the agent server is running before executing API commands.
- Use version-controlled scripts to ensure reproducibility of workflows.

Next Steps
----------

- Combine multiple API calls to create custom data workflows.
- Integrate Curaitor Agent with other Python-based scientific tools.
- Explore advanced features such as custom tool integration and MCP Inspector automation.
