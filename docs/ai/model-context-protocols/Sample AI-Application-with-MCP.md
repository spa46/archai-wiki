# Sample AI Application with MCP

## 1. What is MCP (Model Context Protocol)?

**MCP** stands for **Model Context Protocol**. It is an open protocol designed to standardize how AI models, tools, and agents communicate, share context, and interoperate. MCP enables:
- **Interoperability**: Different AI models and tools can work together seamlessly.
- **Context Sharing**: Models can share and access context (like conversation history, user preferences, etc.).
- **Extensibility**: Easy integration of new tools, models, or agents.

**Use Cases:**
- Building AI assistants that can use multiple models/tools.
- Creating agent frameworks where tools and models can be swapped or extended.
- Standardizing prompt and context management across AI applications.

---

## 2. What is the MCP Python SDK?

The **MCP Python SDK** is a library that implements the MCP protocol in Python. It provides:
- APIs to build MCP-compliant servers (model/tool providers) and clients (applications/agents).
- Utilities for context management, prompt formatting, and tool/resource registration.
- Example implementations for quick start.

Here is a [link to the MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk).

---

## 3. How to Install the MCP Python SDK

### a. Prerequisites
- Python 3.8+
- uv

### b. Installation
```bash
uv add "mcp[cli]"
or
git clone https://github.com/modelcontextprotocol/python-sdk.git
```

### c. Running the standalone MCP development tools
```bash
uv run mcp
```

---

## 4. Example: Running an MCP Server and Client

### a. Example MCP Server

A server provides a model or tool via MCP.

**server.py**
```python
from mcp_sdk.server import MCPServer
from mcp_sdk.resources import TextCompletionResource

class EchoResource(TextCompletionResource):
    def complete(self, prompt, context):
        return f"Echo: {prompt}"

server = MCPServer(resources=[EchoResource()])
server.run(host="0.0.0.0", port=8000)
```

**Run the server:**
```bash
python server.py
```

---

### b. Example MCP Client

A client connects to an MCP server and uses its resources.

**client.py**
```python
from mcp_sdk.client import MCPClient

client = MCPClient("http://localhost:8000")
response = client.complete(prompt="Hello, MCP!", resource="EchoResource")
print(response)
```

**Run the client:**
```bash
python client.py
```

---

## 5. Example: Registering Tools and Resources

**Resource**: A model, tool, or function exposed via MCP.

**Example: Calculator Tool**
```python
from mcp_sdk.resources import ToolResource

class CalculatorResource(ToolResource):
    def run(self, input, context):
        try:
            return str(eval(input))
        except Exception as e:
            return f"Error: {e}"
```
Register this resource with your server as above.

---

## 6. Example: Prompt Engineering

**Prompt**: The input you send to a model/tool.

**Example Prompt for Text Completion:**
```python
prompt = "Write a short poem about the ocean."
response = client.complete(prompt=prompt, resource="TextCompletionResource")
print(response)
```

**Example Prompt for Tool:**
```python
prompt = "2 + 2 * 3"
response = client.run_tool(input=prompt, resource="CalculatorResource")
print(response)
```

---

## 7. Deployment

### a. Deploying the Server

- **Local**: As above, just run `python server.py`.
- **Docker**: (if Dockerfile provided)
  ```bash
  docker build -t mcp-server .
  docker run -p 8000:8000 mcp-server
  ```
- **Cloud**: Deploy to AWS, GCP, Azure, or Heroku as a standard Python web service.

### b. Deploying the Client

- The client can run anywhere with network access to the server.
- For production, package your client as a CLI, web app, or integrate into your backend.

---

## 8. Resources & Tools

- **MCP Python SDK Docs**: (Check the official repo or docs site)
- **Example Repos**: Look for `mcp-python-sdk` on GitHub.
- **Prompt Engineering**: See `docs/ai/prompt-engineering.md` in your project.
- **MCP Protocol Overview**: See `docs/ai/model-context-protocols/overview.md` (you can fill this in with the above info).

---

## 9. Next Steps

1. **Install the SDK** as above.
2. **Create a server** with your own resources/tools.
3. **Create a client** to interact with your server.
4. **Experiment with prompts and tools**.
5. **Deploy** as needed. 