Installation
=====

.. _installation:


Quick Start
----------------

# Install uv
  ```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

# Clone repo
  ```bash
git clone <your-repo-url>
cd curaitor-agent
  ```

# Initialize project
  ```bash
uv init
uv add -r requirements.txt
  ```

# Run web interface
  ```bash
uv run adk web
  ```

Dependency Management
----------------

- Sync when `requirements.txt` is updated:  
  ```bash
  uv sync
  ```

- Add a new package:  
  ```bash
  uv add package-name
  ```
  *(Don’t forget to update `requirements.txt`!)*


MCP Inspector Tool
----------------

The **MCP Inspector** helps verify your MCP server connection and test available tools.  

### Requirements  
- [nvm](https://github.com/nvm-sh/nvm) (Node Version Manager)  
- **Node.js ≥ 18** (v22 recommended)  

### Setup  

1. Install **nvm**:  
   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
   \. "$HOME/.nvm/nvm.sh"
   ```

2. Install **Node.js v22**:  
   ```bash
   nvm install 22
   ```

3. Verify versions:  
   ```bash
   node -v   # v22.19.0
   npm -v    # 10.9.3
   ```

4. Run the MCP Inspector:  
   ```bash
   npx @modelcontextprotocol/inspector uv run tools/mcp_server.py
   ```

5. In the MCP Inspector UI, click **Connect** → test tools.

---

## Notes  
- Ensure you’re using **Node.js v22.x** when running the inspector.  
- Always keep your environment in sync with `requirements.txt` for reproducibility.  

---

## License  
This project is licensed under the **MIT License**.  
